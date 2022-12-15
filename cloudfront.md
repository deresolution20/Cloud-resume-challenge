
- Different ways of pointing a custom domain at S3
- But we're going to use CloudFront only

```yml
  MyDistribution:
    Type: "AWS::CloudFront::Distribution"
    Properties:
      DistributionConfig:
        DefaultCacheBehavior:
          ViewerProtocolPolicy: allow-all
          TargetOriginId: cloud-resume-challenge-bneal.s3-website-us-east-1.amazonaws.com
          DefaultTTL: 0
          MinTTL: 0
          MaxTTL: 0
          ForwardedValues:
            QueryString: false
        Origins:
          - DomainName: cloud-resume-challenge-bneal.s3-website-us-east-1.amazonaws.com
            Id: cloud-resume-challenge-bneal.s3-website-us-east-1.amazonaws.com
            CustomOriginConfig:
              OriginProtocolPolicy: match-viewer
        Enabled: "true"
        DefaultRootObject: index.html
```
