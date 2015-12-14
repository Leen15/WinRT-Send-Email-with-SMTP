# WinRT-Send-Email-with-SMTP
Basic classes for send email with smtp, based on a msdn post (http://blogs.msdn.com/b/mim/archive/2013/11/29/sending-an-email-within-a-windows-8-1-application-using-streamsocket-to-emulate-a-smtpclient.aspx).

With these classes you can easly send an email with smtp protocol.

Here is a simple code for how to do it:


    var client = new SmtpClient()
    {
        Server = "smtp.yandex.com",
        Port = 465,
        IsSsl = true,
        UserName = your_username,
        Password = your_password
    };
    
    var message = new SmtpMessage()
    {
        From = from_address,
        FromName = from_name,
        ReplyTo = reply_address,
        ReplyToName = reply_name,
        Subject = subject,
        Body = body
    };
    message.AddTo(recipient);
    
    await client.SendMail(message);
