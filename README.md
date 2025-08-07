# IdentityServer3 #

## Note: This repository is no longer in active development or maintenance, other than reported security vulnerabilities.
![openid_certified](https://cloud.githubusercontent.com/assets/1454075/7611268/4d19de32-f97b-11e4-895b-31b2455a7ca6.png)

[Certified](http://openid.net/certification/) OpenID Connect implementation.

## Overview ##

IdentityServer is a .NET/Katana-based framework and hostable component that allows implementing single sign-on and access control for modern web applications and APIs using protocols like OpenID Connect and OAuth2. It supports a wide range of clients like mobile, web, SPAs and desktop applications and is extensible to allow integration in new and existing architectures.

[OpenID Connect specification](http://openid.net/specs/openid-connect-core-1_0.html) / [OAuth2 specification](http://tools.ietf.org/html/rfc6749 "OAuth2 specification")

## Getting started ##
IdentityServer is designed as an OWIN/Katana component. By referencing the library or nuget you get a `UseIdentityServer` extension method for `IAppBuilder` that allows setting up IdentityServer in your OWIN host:  

```csharp
public void Configuration(IAppBuilder app)
{
    var options = new IdentityServerOptions
    {
        SigningCertificate = Certificate.Get(),
        Factory = Factory.Create()
    };

    app.UseIdentityServer(options);
}
```

*Note:* If you're hosting in IIS, make sure you enable RAMMFAR in your web.config file.

## Credits ##
IdentityServer is built using the following great open source projects:

- [ASP.NET Web API](https://aspnetwebstack.codeplex.com/)
- [Autofac](http://autofac.org/)
- [Json.Net](http://www.newtonsoft.com/json)
- [LibLog](https://github.com/damianh/LibLog)
- [Katana](https://katanaproject.codeplex.com/)
- [Web Protection Library](https://wpl.codeplex.com/)
- [XUnit](https://github.com/xunit/xunit)
- [License Header Manager](https://visualstudiogallery.msdn.microsoft.com/5647a099-77c9-4a49-91c3-94001828e99e)
