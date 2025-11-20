# AWS Portfolio CI/CD

Static portfolio website with automated AWS S3 deployment using GitHub Actions.

## 💰 Cost: **100% FREE**
✅ AWS Free Tier: 5GB S3 storage + 20,000 GET requests/month  
✅ GitHub Actions: 2,000 minutes/month for public repos  
✅ No charges for static website hosting on S3

## 🚀 Step-by-Step Deployment

### 1. Push to GitHub (FREE)
```bash
# Initialize git in your project folder
cd c:\Users\adity\Desktop\AWS-Portfolio-CICD
git init
git add .
git commit -m "Initial portfolio commit"

# Create repo on GitHub, then:
git remote add origin https://github.com/yourusername/AWS-Portfolio-CICD.git
git branch -M main
git push -u origin main
```

### 2. AWS Setup (FREE TIER) - FIXED BUCKET POLICY
```bash
# Install AWS CLI first: https://aws.amazon.com/cli/
# Configure with your AWS credentials
aws configure

# Create S3 bucket (FREE - stays within 5GB limit)
aws s3 mb s3://your-unique-portfolio-bucket-name

# Enable static website hosting (FREE)
aws s3 website s3://your-unique-portfolio-bucket-name --index-document index.html

# Make bucket public for website (Required for static hosting)
aws s3api put-bucket-policy --bucket your-unique-portfolio-bucket-name --policy '{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-unique-portfolio-bucket-name/*"
    }
  ]
}'
```

### 3. GitHub Secrets Setup
Go to your GitHub repo → Settings → Secrets and variables → Actions → New repository secret:

```
AWS_ACCESS_KEY_ID: Your AWS Access Key
AWS_SECRET_ACCESS_KEY: Your AWS Secret Key  
S3_BUCKET_NAME: adi-pf-2606
```

### 4. Deploy (Automatic)
Push any changes to `main` branch → GitHub Actions deploys automatically!

## 🌐 Your Live Website
After deployment: `http://adi-pf-2606.s3-website-us-east-1.amazonaws.com`

## 📁 Structure
```
├── .github/workflows/deploy.yml    # CI/CD pipeline
├── website/                        # Static files
│   ├── index.html
│   ├── styles.css
│   └── script.js
└── README.md
```

## 🛠️ Local Development
```bash
cd website && python -m http.server 8000
```

## ⚠️ Important Notes
- Bucket name must be globally unique
- Website URL will be: `http://bucketname.s3-website-us-east-1.amazonaws.com`
- FREE as long as you stay under 5GB storage and 20,000 requests/month
- Delete bucket when done to avoid any future charges

## 🌐 Connect
- **Email:** adityarathore2606@gmail.com
- **GitHub:** [@EchoSingh](https://github.com/EchoSingh)
- **LinkedIn:** [adityasinghgdev](https://linkedin.com/in/adityasinghgdev)

✨ **"Building solutions that scale, one line of code at a time."**
