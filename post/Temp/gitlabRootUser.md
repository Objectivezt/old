# gitlab Root 用户切换密码

## 步骤

> 1. `cd /opt/gitlab/bin`
> 2. `sudo gitlab-rails console production`
> 3. `u=User.where(id:1).first`
> 4. `u.password='12345678'`
> 5. `u.password_confirmation='12345678'`
> 6. `u.save!`
