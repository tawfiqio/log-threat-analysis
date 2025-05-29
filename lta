import re
import matplotlib.pyplot as plt

# Example log entry format: "[timestamp] IP: 192.168.1.1 - Login failed"
log_file = "server_logs.txt"

def detect_threats(log_file):
    with open(log_file, "r") as file:
        logs = file.readlines()
    
    failed_attempts = []
    
    for log in logs:
        if "Login failed" in log:
            match = re.search(r"IP: (\d+\.\d+\.\d+\.\d+)", log)
            if match:
                failed_attempts.append(match.group(1))
    
    return failed_attempts

threat_ips = detect_threats(log_file)
print(f"Suspicious IPs: {set(threat_ips)}")

# Visualize frequency of failed attempts
plt.hist(threat_ips)
plt.title("Failed Login Attempts")
plt.show()
