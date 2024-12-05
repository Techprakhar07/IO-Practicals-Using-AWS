# Cross-Account Access in AWS

### Steps to Complete the Practical

1. **Create a Role in the Provider Account**  
   - Go to IAM and create a role with a trust policy for the consumer account.
   - Assign the required permissions.

2. **Use the Role in the Consumer Account**  
   - Assume the role using AWS CLI or SDK.

3. **Verify Access**  
   - Access the provider account resources from the consumer account.
