# Monitoring conversation log status with CloudWatch metrics<a name="conversation-logs-monitoring"></a>

Use Amazon CloudWatch to monitor delivery metrics of your conversation logs\. You can set alarms on metrics so that you are aware of issues with logging if they should occur\.

Amazon Lex V2 provides four metrics in the `AWS/Lex` namespace for conversation logs:
+ `ConversationLogsAudioDeliverySuccess`
+ `ConversationLogsAudioDeliveryFailure`
+ `ConversationLogsTextDeliverySuccess`
+ `ConversationLogsTextDeliveryFailure`

The success metrics show that Amazon Lex V2 has successfully written your audio or text logs to their destinations\. 

The failure metrics show that Amazon Lex V2 couldn't deliver audio or text logs to the specified destination\. Typically, this is a configuration error\. When your failure metrics are above zero, check the following:
+ Make sure that Amazon Lex V2 is a trusted entity for the IAM role\.
+ For text logging, make sure that the CloudWatch Logs log group exists\. For audio logging, make sure that the S3 bucket exists\.
+ Make sure that the IAM role that Amazon Lex V2 uses to access the CloudWatch Logs log group or S3 bucket has write permission for the log group or bucket\.
+ Make sure that the S3 bucket exists in the same region as the Amazon Lex V2 bot and belongs to your account\.