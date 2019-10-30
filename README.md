# terraform-monitor-asg
Terraform to monitor one or more AWS ASGs and alert to Slack if the number of instances in the ASG drops below a threshold

Usage example:
```
variable "slack_webhook_url" {}

module "monitor_asgs" {
  source = "github.com/mozilla-it/asg-alert?ref=tags/1.0"
  slack_webhook_url = "${var.slack_webhook_url}"
  slack_channel     = "it-sre-bot"
  slack_username    = "AWS"
  asgs              = ["testasg", "testasg2"]
}
```
