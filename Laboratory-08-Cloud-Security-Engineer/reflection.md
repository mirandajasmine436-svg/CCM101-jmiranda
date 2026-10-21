# 🪞 Mission Reflection
**Mission 8 — Cloud Security Engineer**

💡 Completing this mission changed how I think about cloud security. Before this lab, I assumed that once a server was deployed, it was "protected." The reality is that a host-based firewall like UFW is a critical layer of defense in depth — even if an attacker breaches the outer network perimeter, UFW on the server still stands between them and the application. By enforcing a Default Deny policy, I ensured the server ignores everything it wasn't explicitly told to accept, which is far more reliable than trying to chase down individual attackers.

🔍 Managing open network ports directly reduces a server's attack surface. Every open port represents a running service with its own vulnerabilities. A MySQL port left open to the world, for example, invites automated brute-force attacks and data exfiltration — no legitimate web user ever needs direct access to a database port. By allowing only ports 22 and 8080, I shrank the number of doors an attacker could try down to two.

😲 The most eye-opening part was realizing how quickly a server gets scanned. In the lab, enabling UFW and then reopening 8080 made the difference between "invisible" and "reachable" very clear. A server exposed to the internet without a firewall is broadcasting its services to every bot on the planet. 

📈 Looking at my portfolio now with eight completed missions, I see a clear progression. From welcoming to the cloud, to infrastructure, operations, and now security, each mission builds on the last. The portfolio now reads like a coherent journey of a cloud engineer growing into a security-conscious professional.
