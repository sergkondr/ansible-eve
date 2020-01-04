# eve-ng

Prepare host and add [Eve-NG](https://www.eve-ng.net/) images.

How to create environment in Google Cloud Platform: [instruction](https://www.eve-ng.net/index.php/documentation/installation/google-cloud-install/)

### Example
Prepare:

* Create `inventory`
```
[eve]
eve.example.com
```

* Fill `group_vars/eve/secret.yaml`
```
---

eve_default_url_s3: "https://s3.eu-west-1.amazonaws.com/bucket.with.images"

telegram_chat_id: "1234567890"
telegram_bot_token: "987654321:ABCDEF...."

r53_updater_zone_id: "Z123412341234"
r53_updater_record: "eve.example.com"
r53_updater_aws_key_id: "AKI123412341234"
r53_updater_aws_secret_key: "..."
```

* Run 
```
# install roles:
ansible-glaxy install -r roles/requirements.yaml
# to install python on new host:
ansible-playbook main.yaml -t python
# configure host
ansible-playbook main.yaml
```

### Todo
* Install eve
* Configure ssh
* Configure sudoers
