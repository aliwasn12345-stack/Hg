# Firebase setup for the home system

This setup keeps the existing `home/` student records and assessment history. Do not switch the database to public read/write.

## One-time Firebase setup

1. In Firebase Console, open **Authentication → Sign-in method** and enable **Email/Password**.
2. In **Authentication → Settings → Authorized domains**, ensure `aliwasn12345-stack.github.io` is listed.
3. In **Realtime Database → Rules**, replace the rules with the contents of `firebase-rules.json`, then click **Publish**.
4. Open `home.html`, choose **Create teacher account**, use `aliwasn12345@gmail.com`, then verify the email from the inbox and sign in.
5. On `student.html`, create an account with an email and password, verify the email, choose **تلميذ** or **ولي أمر**, then submit the student’s full name for linking.
6. In the teacher dashboard, open **طلبات الربط**, verify the identity, choose the account role and existing student record, then approve. This links the account to the existing record without moving or deleting evaluation history. A parent account is separate from the student account; parent-only actions require the approved parent role.
7. When the teacher first opens the dashboard, any old parent PIN is moved into a teacher-only database path; student accounts cannot read it. Parent actions now use the separately approved parent account role.

Passwords are entered only on Firebase's sign-in screen and should never be sent in chat.
