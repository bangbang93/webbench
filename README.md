  Web Bench is very simple tool for benchmarking WWW or proxy servers. Uses fork() for simulating multiple clients and can use HTTP/0.9-HTTP/1.1 requests. This benchmark is not very realistic, but it can test if your HTTPD can realy handle that many clients at once (try to run some CGIs) without taking your machine down. Displays pages/min and bytes/sec. Can be used in more aggressive mode with -f switch.
  The introduction is from official site http://home.tiscali.cz/~cz210552/webbench.html.
  However, Web Bench doesn't support post method. Thus, I modify the file webbench.c to add this method. The parameters now are:
  
  webbench [option]... URL
  -f|--force               Don't wait for reply from server.
  -r|--reload              Send reload request - Pragma: no-cache.
  -t|--time <sec>          Run benchmark for <sec> seconds. Default 30.
  -p|--proxy <server:port> Use proxy server for request.
  -c|--clients <n>         Run <n> HTTP clients at once. Default one.
  -9|--http09              Use HTTP/0.9 style requests.
  -1|--http10              Use HTTP/1.0 protocol.
  -2|--http11              Use HTTP/1.1 protocol.
  --get                    Use GET request method.
  --head                   Use HEAD request method.
  --options                Use OPTIONS request method.
  --trace                  Use TRACE request method.
  --post                   Use POST request method.
  -?|-h|--help             This information.
  -V|--version             Display program version.
  
  when using --post,it is like:
    
    --post="user=codeyz&password=12345"
