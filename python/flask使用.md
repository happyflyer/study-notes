# flask 使用

## 1. flask

```bash
flask run
```

```bash
flask shell
```

```bash
flask routes
```

## 2. flask_babel

```bash
# 抽取翻译文本
pybabel extract -F babel.cfg -k _l -o messages.pot .
# 创建语言
pybabel init -i messages.pot -d app/translations -l zh
# 编译
pybabel compile -d app/translations
# 更新
pybabel extract -F babel.cfg -k _l -o messages.pot .
pybabel update -i messages.pot -d app/translations
```

```bash
# 初始化
flask translate init zh
# 更新
flask translate update
# 编译
flask translate compile
```

## 3. flask_mail

```properties
MAIL_SERVER=smtp.qq.com
# 465 or 587
MAIL_PORT=587
MAIL_USE_SSL=1
MAIL_USERNAME=example@qq.com
MAIL_PASSWORD=authorization_code
MAIL_ADMINS=admin1@163.com,admin2@qq.com
```

```properties
MAIL_SERVER=smtp.163.com
MAIL_USE_SSL=1
MAIL_USERNAME=example@163.com
MAIL_PASSWORD=authorization_code
MAIL_ADMINS=admin1@163.com,admin2@qq.com
```

## 4. flask_migrate

```bash
# 初始化
flask db init
# 迁移
flask db migrate -m "message"
# 升级
flask db upgrade
# 降级
flask db downgrade
```
