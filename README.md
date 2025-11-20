# AWS Portfolio CI/CD

Professional portfolio website with automated AWS S3 deployment using GitHub Actions CI/CD pipeline.

## Architecture Overview

- **Frontend:** Static HTML, CSS, JavaScript
- **Hosting:** Amazon S3 Static Website Hosting
- **CI/CD:** GitHub Actions
- **Cost:** Free Tier (5GB storage, 20K requests/month)

## Deployment Instructions

### Prerequisites
- AWS Free Tier Account
- GitHub Repository
- Basic AWS CLI knowledge

### Setup Process

1. **Repository Setup**
   ```bash
   git clone https://github.com/yourusername/AWS-Portfolio-CICD.git
   cd AWS-Portfolio-CICD
   ```

2. **AWS S3 Configuration**
   ```bash
   aws s3 mb s3://your-bucket-name
   aws s3 website s3://your-bucket-name --index-document index.html
   ```

3. **GitHub Secrets Configuration**
   Navigate to Repository Settings → Secrets and Variables → Actions:
   - `AWS_ACCESS_KEY_ID`
   - `AWS_SECRET_ACCESS_KEY`
   - `S3_BUCKET_NAME`

4. **Automated Deployment**
   Push to main branch triggers automatic deployment via GitHub Actions.

## Project Structure

```
├── .github/workflows/deploy.yml    # CI/CD pipeline configuration
├── website/                        # Static website files
│   ├── index.html                 # Main application
│   ├── styles.css                 # Styling
│   └── script.js                  # Client-side functionality
└── README.md                      # Documentation
```

## Live Application

**URL:** `http://adi-pf-2606.s3-website-us-east-1.amazonaws.com`

## Technical Stack

- **Languages:** HTML5, CSS3, JavaScript ES6
- **Cloud Platform:** Amazon Web Services (S3)
- **CI/CD:** GitHub Actions
- **Deployment:** Automated via AWS CLI

## Development

```bash
cd website
python -m http.server 8000
```

## Maintenance

- Monitor AWS Free Tier usage limits
- Regular dependency updates
- Performance optimization

## Contact

**Aditya Singh**  
Software Engineer | Nokia SWE Intern  
📧 adityarathore2606@gmail.com  
🔗 [GitHub](https://github.com/EchoSingh) | [LinkedIn](https://linkedin.com/in/adityasinghgdev)
