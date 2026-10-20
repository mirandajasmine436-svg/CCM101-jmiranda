# 💭 Mission Reflection — Laboratory 07

🩺 It is absolutely critical to check the host server's resources, even if all your containers appear to be running perfectly, because containers do not exist in a vacuum—they share the host's physical CPU, RAM, and disk space. If a container has a memory leak or a rogue process fills up the server's disk, the entire host machine will crash, taking down every single container with it. Monitoring the host baseline ensures the underlying infrastructure has enough headroom to support the workloads.

🕵️ If a user complains they cannot log into a web application, the `docker logs` command is my best investigative tool. Instead of guessing what is wrong, the logs act as a chronological record of exactly what the user's browser sent and how the server responded. By reviewing the logs, I can immediately see if the user was sending an incorrect password (401 Unauthorized), if the server's backend code crashed (500 Internal Server Error), or if the connection timed out.

⚖️ There is a distinct difference between monitoring logs and monitoring metrics. Logs (Checkpoint 4) are text-based records of discrete events—they tell the "story" of what happened and why. Metrics (Checkpoint 5), like the output from `docker stats`, are numerical measurements over time. Metrics tell you *that* a problem is happening (like CPU usage spiking to 100%), while logs tell you *why* it is happening.

🏢 Large enterprise companies monitor thousands of containers by using centralized observability platforms like Prometheus and Grafana. Prometheus scrapes metric data from all containers, while Grafana turns that data into beautiful, visual dashboards with alerts. For logs, they use stacks like the ELK (Elasticsearch, Logstash, Kibana) to search through millions of log lines in seconds.

💻 My ability to troubleshoot Linux environments has improved tremendously. In Mission 1, I was intimidated by the terminal. Now, I am comfortable using commands like `free`, `df`, `top`, and `docker stats` to diagnose performance issues. I feel like an actual Cloud Operations Engineer.
