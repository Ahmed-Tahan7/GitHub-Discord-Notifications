# **GitHub Actions - Discord PR Notifications & Role Assignment**  

## **Overview**  
This project automates GitHub-Discord integration by:  
- Sending notifications to a Discord channel when a pull request (PR) is opened or closed.  
- Assigning a specific Discord role to users when their PR is merged.  

This helps track contributions and keep the community updated.  

---

## **How to Use**  

### **1. Set Up a Discord Webhook**  
- Go to your Discord **server settings** → **Integrations** → **Webhooks**.  
- Create a webhook and choose a channel for notifications.  
- Copy the webhook URL.  

### **2. Create a Discord Bot**  
- Go to the [Discord Developer Portal](https://discord.com/developers/applications).  
- Create a new bot, enable permissions for managing roles and sending messages.  
- Invite the bot to your server using the generated OAuth2 link.  
- Ensure the bot's role is above the role it will assign.  

### **3. Add GitHub Secrets**  
Go to **GitHub repository settings** → **Secrets and variables** → **Actions**, and add:  
- **Bot Token** (from Discord Developer Portal)  
- **Webhook URL** (for notifications)  
- **Guild (Server) ID**  
- **Role ID** (the role to assign)  

### **4. Map GitHub Users to Discord IDs**  
Since GitHub and Discord usernames are different, create a mapping file with GitHub usernames linked to their Discord IDs.  

### **5. Enable GitHub Actions**  
The workflow file automatically triggers when a PR is opened or closed. It will:  
- Send a message to the Discord channel.  
- Assign a role to the user when the PR is merged.  

### **6. Test the Setup**  
- Open a pull request on GitHub and check for a Discord notification.  
- Merge the PR and verify that the role is assigned.  
- If issues arise, check the GitHub Actions logs for errors.  

---

## **Troubleshooting**  
- If the role is not assigned, check if the bot has the correct permissions and if the GitHub-Discord username mapping is correct.  
- If notifications are not appearing, verify that the webhook URL is correctly set in GitHub secrets.  
- If the GitHub Actions workflow fails, check the logs for missing secrets or incorrect configurations.  

---

## **Future Improvements**  
- Support for tracking other contributions like issues and commits.  
- Adding a leaderboard for top contributors.  
- Automating the GitHub-Discord user linking process.
