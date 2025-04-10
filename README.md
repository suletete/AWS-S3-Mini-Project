

### 1. **Create an S3 Bucket**

   - Log in to your AWS Console.
   - In the search bar, type “S3” and select **S3**.
   - On the S3 Dashboard, click the **Create bucket** button.
   - Provide a unique name for your bucket (e.g., `my-first-s3-bucket-090`).
   - Select the region closest to you.
   - In the **Object Ownership** section, select **ACL Disabled**.
   - **Block all public access** should be checked to ensure security.
   - Keep **Bucket Versioning** disabled at this stage.
   - Click **Create bucket** to finish.

### 2. **Upload a File to S3**

   - On your S3 bucket page (e.g., `my-first-s3-bucket-090`), click on **Upload**.
   - Click **Add files** to select a file from your local machine (for example, create a simple text file, such as `hello.txt`, with "Welcome to the AWS world").
   - After selecting the file, click **Open** and then **Upload**.

### 3. **Enable Versioning**

   - Go to the **Properties** tab of your bucket.
   - Scroll down to the **Bucket Versioning** section.
   - Click **Edit** and select **Enable**.
   - Click **Save changes** to enable versioning.

### 4. **View Object Versions**

   - After enabling versioning, upload the file again (either with changes or as a duplicate).
   - In the **Objects** section, click **Show versions** to view both versions of the file.

### 5. **Set Bucket Permissions to Allow Public Access**

   - In the **Permissions** tab of your bucket, click **Edit** under **Block public access**.
   - Uncheck **Block all public access** and type **confirm** to confirm.
   - Click **Save changes**.

### 6. **Create a Bucket Policy for Public Access**

   - In the **Permissions** section, click on **Bucket Policy**.
   - Use the **Policy generator** tool to create a policy:
     - **Policy type**: S3 Bucket Policy.
     - **Effect**: Allow.
     - **Principal**: `*` (this means all users).
     - **Actions**: Select `s3:GetObject` and `s3:GetObjectVersion`.
     - **Amazon Resource Name (ARN)**: Enter the ARN of your bucket, like `arn:aws:s3:::my-first-s3-bucket-090/*`.
   - Click **Add statement** and then **Generate Policy**.
   - Copy the generated policy and paste it into the **Bucket Policy** editor.
   - Click **Save changes**.

### 7. **Set Lifecycle Policy (Optional)**

   - In the **Management** tab of your bucket, click **Create lifecycle rule**.
   - Define a rule to manage object transitions (e.g., moving older files to cheaper storage classes like Glacier).
   - You can also set a policy to delete objects after a certain period.

### Final Notes:
After completing these steps, you will have:
- Created an S3 bucket.
- Uploaded a file to that bucket.
- Enabled versioning to keep track of different file versions.
- Configured permissions for public access.
- Optionally, set lifecycle policies to manage storage costs.


