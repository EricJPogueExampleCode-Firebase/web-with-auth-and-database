# Add yourdomain.com or firebase.yourdomain.com to Firebase Hosting

1. Open the [Firebase Console](https://console.firebase.google.com/) and go to **Hosting**.
2. Click **Add custom domain**.
3. Enter `yourdomain.com` (root domain) or `firebase.yourdomain.com` (subdomain) and continue.
4. If Firebase asks whether to redirect the domain to an existing website, do not choose redirect. Set up the domain to use Firebase Hosting directly.
5. Firebase provides DNS records to add in GoDaddy.
6. Open **GoDaddy → My Products → Domains → yourdomain.com → Manage DNS**, and add the DNS records Firebase gives you:

   **For a subdomain:**

   | Type | Name | Value | TTL |
   |---|---|---|---|
   | CNAME | firebase | yourapp.web.app | 1 hour |

   **For a root domain:**

   | Type | Name | Value | TTL |
   |---|---|---|---|
   | A | @ | IP address provided by Firebase | 1 hour |
   | TXT | @ | Verification value provided by Firebase | 1 hour |

7. Return to Firebase Hosting and check the domain status. DNS verification may take time.
8. Wait for Firebase to finish setting up the domain and its HTTPS certificate.
9. Test the website at `https://yourdomain.com` or `https://firebase.yourdomain.com`.

**Important:** If the domain already points to another hosting provider, you may need to remove or replace conflicting DNS records before connecting it to Firebase Hosting.
