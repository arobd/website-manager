# Website manager

I will update description later. 

## Installation

**Prerequisites**

Register and get an API Key from Whois XML API: https://main.whoisxmlapi.com/. It is FREE (500 requests per month and that is enough).

**Lets start**

Clone the project 

`git clone https://github.com/raselupm/website-manager.git`

Go to project 

`cd website-manager`

Rename .env.example to .env & Add your WHOIS XML API key on **WHOISXML_APIKEY** variable. Also add your database info. Additionally, you can add SMTP information for get emails when website down or up.

Install composer

`composer install`

Migrate database

`php artisan migrate`

Generate application key 

`php artisan key:generate`

Since we disabled registration, you might want to create a user. You can use tinker or whatever you prefer.

After doing all fo these, serve the application

`php artisan serve`

You also need to run a cron job for running uptime checker every minute. You can do these ways: 

**On localhost**

Make a new tab on terminal & run command below

`php artisan schedule:work`

You will start seeing schedules in every one minute. It will automatically check all websites every minutes. 

**On Server**

You can easily do via cron, on terminal, run command

`crontab -e`

Then add this line: 

`* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1`

Save & exit. 


## Disclaimer

This application made as learning purpose. Please don't make this comment when we meet face to face **"Bhai ki sob noob code likhcen, abar vab nen apni birat programmer"**. Thank in advance.


## Contributing

Yes, you are welcome to do that. Please send me requests. Thank you. 


## Security Vulnerabilities

Bhaire, if this application make apnar server down or anything, amar kisu korar nai, ami notun code shikhci & swami bidesh. 

## License

The code is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
