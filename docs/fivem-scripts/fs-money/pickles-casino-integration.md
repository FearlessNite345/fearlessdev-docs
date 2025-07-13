---
id: pickle_casino-integration
sidebar_label: Pickle_casino Integration
sidebar_position: 2
---

# 🎰 FS-Money Integration with Pickles Casino

This guide explains how to integrate **Pickles Casino** with your **FS-Money** script so all casino transactions use FS-Money balances.  

We’ve provided a ready-to-use integration package to make the process quick and easy.  

---

## 📥 Download Integration Files

Click the button below to download the integration package:  

<a href="https://your-direct-zip-link-here" style="display: inline-block; background-color: #BA2323; color: white; padding: 10px 20px; border-radius: 8px; text-decoration: none; font-weight: bold;">⬇️ Download Integration Files</a>

---

## 🛠️ Installation Steps

1. **Download the integration ZIP** using the button above.  
2. Extract the contents of the ZIP.  
3. Copy all files into the `pickle_casino/bridge` folder in your server’s resources. Overwrite any existing files if prompted.  
4. Open your `server.cfg` and ensure these resources are started in the following order **(this is required for proper integration)**:  

    ```txt
    ensure fs-money
    ensure pickle_casino
    ```

5. Restart your server to apply the changes.  

---

## ✅ Integration Complete

Your **Pickles Casino** is now connected to **FS-Money**, and all payouts and player transactions will flow through FS-Money.  

---

### 🆘 Need Help?  
If you encounter any issues:  
- Open an issue on [GitHub](https://your-github-repo-link-here)  
- Or join our Discord for support: [Join Discord](https://your-discord-invite-link)  
