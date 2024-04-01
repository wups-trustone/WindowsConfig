- [font](#font)
- [ssh](#ssh)

## font<a id="font"></a>

[MicrosoftYaHeiMono-CP950](https://github.com/doggy8088/MicrosoftYaHeiMono-CP950)

## ssh<a id="ssh"></a>

Connect to remote with key pair.

1. Copy .ssh folder to %USERPROFILE%.

   ```cmd
   CMD> xcopy /E /Y /I .ssh %USERPROFILE%\.ssh
   ```

2. Create key pair.

   ```cmd
   CMD> ssh-keygen -f %USERPROFILE%\.ssh\keys\<user>@<remote>
   ```

3. Copy public key to remote.

   ```cmd
   CMD> scp %USERPROFILE%\.ssh\keys\<user>@<remote>.pub <user>@<remote>:~/key.pub
   CMD> ssh <user>@<remote> -C "mkdir -p ~/.ssh; cat ~/key.pub >> ~/.ssh/authorized_keys; rm ~/key.pub"
   CMD> del %USERPROFILE%\.ssh\keys\<user>@<remote>.pub
   ```