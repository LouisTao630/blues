# 获取客户端真实IP
一个简单的网络连接中，用户直接连接上服务器。那么远端的IP就是客户端IP。然而，在实际网络中，为了更好的保护服务器，往往使用NGINX作为反向代理服务器。那么连接服务器的远端IP则是代理服务器的IP地址，而真正的用户IP自然就获取不到了。为此，需要增加额外的标示来保存真正客户端的IP地址。
## Remote-IP
最直接的表示连接的客户端IP。如果客户端和服务器之间有代理服务器，那么此字段表示的是代理服务器的IP。◊

## x-real-ip
此字段非标准字段，确实可以标示真正连接的客户端。但是，当网络存在两层以上代理时，此值可能为上一层代理服务器的值。所以，使用此字段需要特别小心。

## X-Forwarded-For
此字段是标准的协议头，用来表示请求中代理路径，通过逗号+空格分割每一层的代理。可以使用它来找到客户端IP，即使是在多层代理当情况下。
当然，因为这个字段很容易被伪造，所以从安全性角度考虑，这个IP的真实性还存在疑虑。
