
### **Step 1: Create an S3 Bucket**

1. **Log in to AWS Console**:
   - Open your browser and go to the AWS Management Console: [https://aws.amazon.com/](https://aws.amazon.com/).
   - Log in using your credentials.

2. **Navigate to S3**:
   - In the AWS Console search bar, type **S3** and select **S3** under **Services**.

3. **Create a Bucket**:
   - Once you're on the **S3 Dashboard**, click the **Create bucket** button.
   - Fill in the bucket details:
     - **Bucket name**: `my-first-s3-bucket-090` (You can change this name, but make sure it's globally unique).
     - **Region**: Choose a region close to your location (e.g., US East (N. Virginia)).
   
4. **Configure Bucket Settings**:
   - Under **Object Ownership**, select **ACL Disabled**.
   - Under **Block Public Access settings for this bucket**, make sure all options are checked (this blocks public access).
   
5. **Create the Bucket**:
   - Scroll down and click **Create bucket**.

### **Step 2: Upload a File to the Bucket**

1. **Go to Your Bucket**:
   - After creating the bucket, click on the name `my-first-s3-bucket-090` to open the bucket.

2. **Upload a File**:
   - In the **Objects** tab, click on the **Upload** button.
   - Click **Add files** to select a file from your local system. For example, create a file named `hello.txt` with the text "Welcome to AWS S3!".
   - Click **Open** to select the file, then click **Upload**.

### **Step 3: Enable Versioning**

1. **Go to Bucket Properties**:
   - While in your bucket, click on the **Properties** tab.

2. **Enable Versioning**:
   - Scroll down to **Bucket Versioning**.
   - Click **Edit** and select **Enable** to turn on versioning.
   - Click **Save changes**.

   Versioning allows you to keep multiple versions of the same file in your bucket. This is useful for tracking file changes.

### **Step 4: View Object Versions**

1. **Upload the File Again**:
   - In the **Objects** tab, upload the file `hello.txt` again, but make a small change (e.g., change the text to "Hello, AWS S3!").
   
2. **View Versions**:
   - Click on the **Show versions** button to see both versions of the file. AWS keeps track of the previous and current versions of the same object.

### **Step 5: Set Bucket Permissions to Allow Public Access**

1. **Go to Permissions**:
   - Click on the **Permissions** tab of your bucket.

2. **Disable Public Access Block**:
   - Scroll down to **Block public access (bucket settings)**.
   - Click on **Edit** and uncheck **Block all public access**. AWS will ask you to confirm this action. Type `confirm` in the box to proceed.
   - Click **Save changes**.

   This will allow public access to the files in your bucket. This is useful if you want others to access the files via a URL.

### **Step 6: Create a Bucket Policy for Public Access**

1. **Go to Bucket Policy**:
   - In the **Permissions** tab, click on **Bucket Policy**.

2. **Generate a Policy**:
   - Use the following policy to allow public access to your files:
   
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::my-first-s3-bucket-090/*"
           }
       ]
   }
   ```

   - Replace `my-first-s3-bucket-090` with your bucket name if you use a different one.
   - Click **Save** to apply the policy.

   This policy allows anyone to view the objects (files) stored in your bucket.

### **Step 7: Set Lifecycle Policy (Optional)**

1. **Go to Management Tab**:
   - In the **Management** tab of your bucket, click on **Create lifecycle rule**.

2. **Define Lifecycle Rule**:
   - Give the rule a name, like `ExpireOldFiles`.
   - Under **Lifecycle rule actions**, you can define actions like deleting objects after a set number of days. For example, you could delete files older than 30 days.
   
   Example:
   - **Expire current versions of objects**: After 30 days, delete the file.

3. **Save Rule**:
   - Click **Create rule** to save and apply the lifecycle policy.

---

### **Conclusion**

Now, your S3 bucket is fully set up. Here’s a recap of what you’ve done:
1. Created a bucket (`my-first-s3-bucket-090`).
2. Uploaded a file to the bucket.
3. Enabled versioning to track file changes.
4. Set public access permissions and a bucket policy.
5. Optionally set a lifecycle policy for file management.

