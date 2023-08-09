# Challenge:

The website seems to be under maintenance.

Flag format LITCTF{...}

# Solution:

After reading the source code, we know that we get command injection but they we can't saw the output

```
@app.route('/', methods = ['GET','POST'])
def index():
    output = None
    if request.method == 'POST':
        hostname = request.form['hostname']
        cmd = "ping -c 3 " + hostname
        output = os.popen(cmd).read()

    return render_template('index.html', output='The service is currently under maintainence and we have disabled outbound connections as a result.')
```
So this it blind command injection. The first thing i think about is using time base to get the flag. Try `; sleep 5` we saw that it actully sleep.
Google and we get some payload like this: `if [ $(cat flag.txt|cut -c 1) == L ]; then sleep 5; fi` but when run it fail. The first character of the flag for sure is `F`.
Aftersome try i think it may happen because if can't run in here 🤦‍♂️. So how can we run something to sleep when we get the right character?
It's using pipping in linux and syntax to run multiple command. This payload will work: `; cat flag.txt| cut -c 1| grep -q F&& sleep 5`.
The command first close the ping using `;` then it `cat flag.txt`, using this result to get the first character in the flag using `cut -c 1` after that `grep -q F` to check if that letter F or not.
Finally, using `&&` to check if previous is error or not. If error, notthing happen but if success the server will sleep in 5s seconds `sleep 5`.

Time to use intruder in burp to get the flag. Remember to use column -> response recived to see the time they response.

Flag: `LITCTF{c4refu1_fr}`

# ENJOY🤡
