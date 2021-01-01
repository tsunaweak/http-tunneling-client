# http-tunneling-client
Cross platform http tunneling client


How to Use:

OpenVPN with HTTP Tunneling

Add this on your OpenVPN Config File -> http-proxy 127.0.0.1 8228

Bitvise SSH Client
On Proxy Settings set the proxy server as 127.0.0.1 and port as 8228 then select proxy  type as HTTP


Direct
./http-tunnel-client-win.exe -lp 8228 -payload "CONNECT [host_port] [protocol][crlf][crlf]" -rp "127.0.0.0:8080" -tunType "HTTP"

HTTP Payload
./http-tunnel-client-win.exe -lp 8228 -payload "CONNECT [host_port] [protocol][crlf][instant_split]GET http://google.com/  HTTP/1.1[crlf]Host: google.com[crlf]X-Online-Host: google.com[crlf]X-Forward-Host: google.com[crlf]Connection: Keep-Alive[crlf][crlf]" -rp "127.0.0.0:8080" -tunType "HTTP"

SSL Tunnleing
./http-tunnel-client-win -lp 8228 -sni "google.com"  -tunType "SSL"

Note:
Change the -rp value to your desired remote proxy server
Change the -lp value to your desired local proxy port 
