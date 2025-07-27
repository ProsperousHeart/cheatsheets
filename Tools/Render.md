# Table of Contents

1. [Purpose](#purpose)

2. [Pricing Data](#pricing-data)

3. [Connecting to Render Postgres DB](#connecting-to-render-postgres-database)

4. [Additional Helpful Documentation](#additional-helpful-documentation)

# Purpose

This markdown will provide information on utilizing Render for your projects.

For more information, please utilize [their documentation](https://render.com/docs).

Note that you can have multiple databases using the same instance as per [here](https://render.com/docs/postgresql-creating-connecting#adding-multiple-databases-to-a-single-instance).

# Pricing Data

There is also [pricing](https://render.com/pricing#postgresql) to be considered, so be sure you understand what is required when setting up your connection. You can learn more about the free options [here](https://render.com/docs/free).

There is a [free databsae option](https://render.com/docs/free#free-postgres), but it is deleted after 30 days if you do not convert to a paid database.

Concerned about spending too much when using pipelines? You can set a limit per [here](https://render.com/docs/build-pipeline#setting-a-spend-limit).

They've also lowered pricing on bandwidth usage as per [here](https://render.com/blog/new-bandwidth-pricing-on-render).

# Connecting to Render Postgres Database

If you have not already made a postgres database on Render, you will need to do so as per [here](https://render.com/docs/postgresql-creating-connecting#create-your-database).

Note that you also have the option to add multiple databases to your Postgres instance per [here](https://render.com/docs/postgresql-creating-connecting#adding-multiple-databases-to-a-single-instance). (Still needs to be in the limitations of your pricing tier.)

Once you have your database set up, you will follow this process to connect from your local pgAdmin program via an [external connection](https://render.com/docs/postgresql-creating-connecting#external-connections).

1. Access the dashboard for your postgres service

2. In the **Info** section, scroll down to the **Connections** section:

    ![DB Connections info](/Tools/IMGs/render-connections.png)

    You will need to utilize the following details:
    - port
    - username
    - password
    - database
    
    Note that you can also extract this from the external database URL, which is in the format of:
    
    `postgresql://USER:PASSWORD@INTERNAL_HOST:PORT/DATABASE`

3. Open up your [pgAdmin](https://www.pgadmin.org/) software.

4. Right-click on **Servers** and choose **Register > Server...**

    ![regsiter new server](/Tools/IMGs/register-server.png)

5. Under the initial **General** tab, provide a new server name.

    ![register server - general tab](/Tools/IMGs/reg-srvr-general.png)

    You can add comments if you wish to help you remember what the server is for.

6. Under the **Connection** tab you'll see a screen like this:

    ![register server - connection tab](/Tools/IMGs/reg-srvr-connection.png)

    You'll need to update the following:

    - **Host name/address** is not just the hostname found in your Render dashboard. Easiest way to update this field is to pull it from the external URL:
    
        `postgresql://USER:PASSWORD@INTERNAL_HOST:PORT/DATABASE`

    - **Port** seems to be the same, but update it if different in Render dashboard.

    - **Maintenance database** is the database found in the Render dashbaord as well as in the last piece of the external URL

    - **Username** and **Password** are the same as what's in the Render dashboard

7. Once you have filled in this information and hit the **Save** button, it should connect to the database.

    ![confirming server connected](/Tools/IMGs/connected-server.png)

# Additional Helpful Documentation

Using Django? Check [this](https://render.com/docs/deploy-django) out! (As well as the official Django [deployment checklist](https://docs.djangoproject.com/en/5.0/howto/deployment/checklist/).)

If you are also looking to do Infrastructure as Code (IaC) check [this](https://render.com/docs/infrastructure-as-code) out.