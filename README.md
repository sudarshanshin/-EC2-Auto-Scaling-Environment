# AWS Project Assignment -- Question 3

## EC2 Auto Scaling Environment

### Objective

Configure an EC2 Auto Scaling environment using an EC2 Launch Template,
an Auto Scaling Group, and CloudWatch metrics. The environment launches
a Linux web server automatically and demonstrates capacity changes.

### AWS Services

-   Amazon EC2
-   EC2 Launch Template
-   EC2 Auto Scaling Group
-   Amazon CloudWatch
-   EC2 Security Groups

### Configuration

  -----------------------------------------------------------------------
  Setting                             Value
  ----------------------------------- -----------------------------------
  AWS Region                          `us-east-1` (as shown in the
                                      console screenshots; confirm this
                                      matches your deployed resources)

  Launch Template                     `ASG-Web-Template` (update if your
                                      actual name differs)

  Auto Scaling Group                  `My-Web-ASG` (update if your actual
                                      name differs)

  Minimum capacity                    1

  Desired capacity                    2

  Maximum capacity                    4

  Scaling policy                      Target tracking

  Metric                              Average CPU utilization

  Target CPU                          50%

  Web server                          Apache HTTP Server
  -----------------------------------------------------------------------

### Implementation Steps

1.  Created a security group with HTTP access on TCP port 80 and
    restricted SSH access on TCP port 22.
2.  Created a Launch Template using a Linux AMI and configured User Data
    to install and start Apache.
3.  Created an Auto Scaling Group using the Launch Template.
4.  Set minimum, desired, and maximum capacity values.
5.  Configured a CPU target-tracking scaling policy.
6.  Connected to the Linux instance and installed/configured the web
    server.
7.  Checked CPU utilization and scaling activity in CloudWatch and the
    Auto Scaling Group activity history.

### Screenshot Location

The screenshot folder shown in Windows File Explorer is:

`Desktop\clouds Projects\que 3\screenshots`

For a portable submission, keep the screenshots in a folder named
`screenshots` beside this README. Example relative path:

`./screenshots/`

The uploaded File Explorer photo shows these screenshot file labels: -
`asg1` - `capacity` - `cpu utilty` - `desired capacity` - `graph` -
`instance` - `launch template` - `region` - `review` - `run` -
`security gp` - `vpc`

Make sure the actual screenshot files are copied into the `screenshots`
folder and use clear extensions such as `.png` or `.jpg`. The File
Explorer photo is a view of the folder, not proof of the CloudWatch
graph contents.

### Testing Results

Fill in the actual result after testing:

  -----------------------------------------------------------------------
  Test                                Expected / observed result
  ----------------------------------- -----------------------------------
  Launch Template                     Created

  Auto Scaling Group                  Created

  Initial EC2 instances               Record actual count and status

  Apache web page                     Record whether reachable over HTTP

  Desired capacity changed            Record whether the requested
                                      instance count was reached

  CPU target tracking                 Record actual scaling action, if
                                      any

  CloudWatch CPU metric               Attach the actual CPUUtilization
                                      graph
  -----------------------------------------------------------------------

### Conclusion

This project demonstrates automated EC2 provisioning and capacity
management using AWS Auto Scaling and CloudWatch. Record only scaling
actions and test outcomes that were actually observed.

### Cleanup

After collecting evidence, delete the Auto Scaling Group and verify that
its EC2 instances have terminated. Remove unused launch templates and
security groups when no longer needed, and check AWS Billing for
remaining resources.
