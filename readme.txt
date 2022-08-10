aws cloudformation create-stack  --stack-name project2 --region us-east-1 --template-body file://project2.yml --parameters file://project2-parameters.json

  BastionHost:
    Description: This is BastionHost
    Value: !Ref BastionHost
    Export:
      Name: !Sub "${!GetAtt BastionHost.PublicIp} -is ip Public of BastionHost" 


    
Export:
      Name: !Sub "http://${!GetAtt WebAppLB.DNSName}"