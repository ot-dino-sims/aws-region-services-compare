aws-region-services-compare
I used windows wsl ubuntu with bash shell to do this. AWS-CLI was installed. I ran this against the aws root account.

Do the usual to access the aws account profile using okta cli.
okta_aws {enter the usual when prompted}
okta_aws XXX {set aws profile to our okta root account}

I used this AWS link provided by AWS support that shows AWS Regional Services Lists: [http://servicesaws.amazon.com/](http://servicesaws.amazon.com/)

I scrapped the services of us east 1 and us east 2 off the web page into two files.
Which yielded a list of Services for us-east-1 and us-east-2 as of 21 November 2022:
208 us-east-1-service-list.txt
181 us-east-2-service-list.txt

Then I ran a diff against both lists to show the delta's.
There are 27 Services not in us-east-2 as of 21 November 2022 today:

$ diff -y us-east-1-service-list.txt us-east-2-service-list.txt|grep '<'
AWS Application Discovery Service                             <
AWS Cost Explorer                                             <
AWS Cost and Usage Report                                     <
AWS Data Pipeline                                             <
AWS DeepComposer                                              <
AWS DeepLens                                                  <
AWS DeepRacer                                                 <
AWS Elemental MediaStore                                      <
AWS Elemental MediaTailor                                     <
AWS IoT TwinMaker                                             <
AWS Mainframe Modernization                                   <
AWS Migration Hub                                             <
Alexa for Business                                            <
Amazon Braket                                                 <
Amazon CloudSearch                                            <
Amazon Connect                                                <
Amazon Elastic Transcoder                                     <
Amazon IVS                                                    <
Amazon Lex                                                    <
Amazon Managed Blockchain                                     <
Amazon Nimble Studio                                          <
Amazon RDS on VMware                                          <
Amazon WorkDocs                                               <
Amazon WorkMail                                               <
Amazon WorkSpaces                                             <
Amazon WorkSpaces Application Manager                         <
Amazon WorkSpaces Web                                         <
