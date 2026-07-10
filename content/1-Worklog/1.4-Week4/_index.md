---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---
### Week 4 Objectives:
* Deploy a LAMP (Linux, Apache, MySQL, PHP) stack web hosting environment on the EC2 instance.
* Retrieve, extract, and configure WordPress installation files.
* Edit `wp-config.php` to integrate WordPress with the isolated Amazon RDS MySQL instance.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | --- | --- | --- | --- |
| 2 | - Connect to EC2 via SSH and update repository configurations. <br> - Install Apache2 Web Server and verify the default landing page. | 11/05/2026 | 11/05/2026 | [Installing Apache2 on Ubuntu](https://ubuntu.com/tutorials/install-and-configure-apache) |
| 3 | - Install PHP alongside essential extensions (php-mysql, php-gd, php-xml, etc.). <br> - Create an `info.php` file to test and verify successful script processing. | 12/05/2026 | 12/05/2026 | [AWS LAMP Server Installation Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-lamp-amazon-linux-2023.html) |
| 4 | - Download the latest WordPress distribution package from WordPress.org. <br> - Extract source files to `/var/www/html/` and configure correct write privileges for `www-data`. | 13/05/2026 | 13/05/2026 | [WordPress Download & Tar extraction](https://wordpress.org/download/) |
| 5 | - Edit the `wp-config.php` file inside the WordPress root directory. <br> - Define `DB_NAME`, `DB_USER`, `DB_PASSWORD`, and direct `DB_HOST` to the RDS Endpoint. | 14/05/2026 | 14/05/2026 | [Editing wp-config.php](https://developer.wordpress.org/advanced-administration/wordpress/wp-config/) |
| 6 | - Configure Apache Virtual Hosts and enable the URL rewriting module. <br> - Access the website public IP, run the WordPress web installation wizard, and post a test blog. | 15/05/2026 | 15/05/2026 | [WordPress Installation Handbook](https://developer.wordpress.org/advanced-administration/before-install/howto-install/) |

### Week 4 Achievements:
* Fully installed and optimized a LAMP stack (Apache web server, PHP, MySQL client utilities) on the Ubuntu Linux server.
* Successfully set up WordPress configuration requirements including directory write permissions and URL rewrite configurations.
* Integrated the front-end application layer (EC2) with the back-end database layer (RDS) by modifying `wp-config.php`.
* Deployed a fully functional WordPress website accessible via the server's public Elastic IP address.
