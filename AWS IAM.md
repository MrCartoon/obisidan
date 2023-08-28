[[AWS IAM|IAM]] - Identity and Access Management ^desc
- User - real user or programmatic access to the AWS using personal credentials
- Group - aggregation of users to assign same policies
- Role - per-service/per-resource automatic authorization to the AWS (for instance EC2 can pull image from ECR without providing docker credentials) Also allows cross account/organization access. Users can assume role if it's allowed by role
- Policy - access rules with possibility to configure conditions. Assigned to User, Group or Role.
