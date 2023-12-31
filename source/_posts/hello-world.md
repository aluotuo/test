---
title: Hello World
categories:
  - 其他
tags:
  - 其他
---
Welcome to [Hexo](https://hexo.io/)! This is your very first post. Check [documentation](https://hexo.io/docs/) for more info. If you get any problems when using Hexo, you can find the answer in [troubleshooting](https://hexo.io/docs/troubleshooting.html) or you can ask me on [GitHub](https://github.com/hexojs/hexo/issues).

## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)

```java
@Slf4j
@RestController
@RequestMapping
@RequiredArgsConstructor
public class LoginController {

    private static final String JWT_HEADER_KEY = "authorization";
    private static final String JWT_HEADER_PREFIX = "Bearer ";
    private final LoginService loginService;

    @PostMapping(value = "/login", name = "用户账户#登录")
    @ExtendLogging(object = {"username:账户"})
    public LoginResponse login(@RequestBody LoginRequest loginRequest, HttpServletResponse response) {
        LoginResponse result = loginService.login(loginRequest);
        response.setHeader(JWT_HEADER_KEY, JWT_HEADER_PREFIX + result.getToken());
        return result;
    }
}
```
