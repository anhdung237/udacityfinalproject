# Pipeline Process
- Modify code
- Stage all changes: `git add .`
- Commit chages: `git commit -m "message"`
- Push all commits: `git push`
- Pipeline will be triggerd automatically after pushed
- Pipeline run Build phase:
1. Setup environment
2. Install dependencies for udagram-frontend
3. Install dependencies for udagram-api
4. Check lint for udagram-frontend
5. Build udagram-frontend
6. Build udagram-api
- Pipeline go into Hold phase, need to go to CireCI to approve in order to deploy
- Click Approve
- Pipeline run Deploy phase:
1. Setup environment
2. Setup EB
3. Setup AWS-CLI
4. Checkout code
6. Pass secrets from CircleCI to EB
7. Deploy udagram-api 
8. Deploy udagram-frontend