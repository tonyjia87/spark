---
description: Install ProcessMaker on premises.
---

# Install ProcessMaker

{% hint style="warning" %}
The following installation instructions are for the ProcessMaker Community edition internal beta. The internal beta is a developer-oriented installation procedure.

The installation procedure described below installs prerequisite applications and then installs the internal beta for ProcessMaker 4 Community edition.

Ensure you meet [installation requirements](prerequisites.md) prior to starting this installation procedure.
{% endhint %}

## Install Prerequisites

### Update Packages

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="Update your packages system." %}
```text
apt-get update && apt-get upgrade
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

In order to install ProcessMaker 4 you will need the following:

* [VirtualBox 5.2.22](install-processmaker-on-premise.md#install-virtualbox-5-2-22)
* [Vagrant 2.2.2](install-processmaker-on-premise.md#install-vagrant-2-2-1)
* [PHP 7.2](install-processmaker-on-premise.md#install-php-7-2)
* [Composer](install-processmaker-on-premise.md#install-composer)
* [Node.js 10.13.0](install-processmaker-on-premise.md#install-node-js-10-13-0)

### **Install VirtualBox 5.2.22**

[Download VirtualBox](https://www.virtualbox.org/wiki/Linux_Downloads) for your Linux distribution.

![Download the VirtualBox installer for your Linux distribution](../.gitbook/assets/vitualbox-download.png)

Install the VirtualBox package using one of the following commands depending on your Linux distribution to which you are installing VirtualBox:

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="1. Install the VirtualBox package." %}
```text
dpkg -i [file name].deb
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

{% code-tabs %}
{% code-tabs-item title="2. Verify VirtualBox installed correctly." %}
```text
virtualbox -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}

After the installation finishes, VirtualBox sometimes does not work because of missing dependencies. If this happens, run the following command:

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="2a. Install the missing dependencies." %}
```text
sudo apt-get -f install 
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

After installing missing dependencies, recompile the kernel module:

{% code-tabs %}
{% code-tabs-item title="2b. Recompile the kernel module after installing missing dependencies." %}
```text
sudo /sbin/vboxconfig
```
{% endcode-tabs-item %}
{% endcode-tabs %}

If VirtualBox notifies you again of missing dependencies, install the libraries for gcc, make, and perl:

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="2c. Install the libraries for gcc, make and perl." %}
```text
apt-get install gcc make perl
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

After you install the libraries, recompile the kernel module \(command 2b above\). If VirtualBox continues to notify you of missing dependencies, install the kernel module that corresponds with the error and then recompile the kernel module.

For example:

{% tabs %}
{% tab title="Debian 9" %}
{% code-tabs %}
{% code-tabs-item title="Install kernel module." %}
```text
apt-get install linux-headers-4.9.0-4-amd64
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Ubuntu 16.04" %}
{% code-tabs %}
{% code-tabs-item title="Install kernel module." %}
```text
apt-get install kernel-devel
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Ubuntu 18.04" %}
{% code-tabs %}
{% code-tabs-item title="Install kernel module." %}
```text
apt-get install linux-headers-generic
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

{% hint style="info" %}
The error message notifies you which steps to perform if none of the commands above worked.
{% endhint %}

Verify that VirtualBox works correctly after you successfully install it.

### Install Vagrant 2.2.2

[Download Vagrant](https://www.vagrantup.com/downloads.html) for your Linux.

![](../.gitbook/assets/vagrant-download.png)

Use the following command to install Vagrant:

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="Install Vagrant." %}
```text
dpkg -i [file name].deb
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

Verify that Vagrant is installed correctly:

{% code-tabs %}
{% code-tabs-item title="Verify it is the correct version." %}
```text
vagrant -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Install PHP 7.2

{% tabs %}
{% tab title="Debian / Kali" %}
{% hint style="info" %}
If your Linux distribution already has PHP 7.2 you do not need to add the repository. Go directly to the "Install PHP 7.2 and modules" command below \(command 3\).
{% endhint %}

Perform the following commands to install PHP 7.2:

{% code-tabs %}
{% code-tabs-item title="1. Download and add the repository." %}
```text
wget -q https://packages.sury.org/php/apt.gpg -O- | sudo apt-key add -
echo "deb https://packages.sury.org/php/ stretch main" | sudo tee /etc/apt/sources.list.d/php.list
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Run the `update` and `upgrade` command:

{% code-tabs %}
{% code-tabs-item title="2. Update and upgrade the package system." %}
```text
sudo apt-get update && apt-get upgrade
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
If the following error displays:

```text
Reading package lists... Done
E: The method driver /usr/lib/apt/methods/https could not be found.
N: Is the package apt-transport-https installed?
E: Failed to fetch https://packages.sury.org/php/dists/stretch/InRelease
E: Some index files failed to download. They have been ignored, or old ones used instead.
```

Install the following program to install HTTPS certificates and protocols:

{% code-tabs %}
{% code-tabs-item title="Install HTTPS certificates and protocols." %}
```text
sudo apt-get install ca-certificates apt-transport-https
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Note that using this command overwrites the symlink with the correct files.
{% endhint %}

{% code-tabs %}
{% code-tabs-item title="3. Install PHP 7.2 and modules." %}
```text
sudo apt-get install php7.2 php7.2-cli php7.2-common php7.2-opcache php7.2-curl php7.2-mbstring
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="4. Verify the installation." %}
```text
php -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Mint / Ubuntu" %}
Perform the following commands to install PHP 7.2:

{% code-tabs %}
{% code-tabs-item title="1. Install the program to add repositories." %}
```text
apt-get install software-properties-common
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="2. Add the repository." %}
```text
add-apt-repository ppa:ondrej/php
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="3. Update the packages." %}
```text
apt-get update
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="4. Install the PHP 7.2 version and its modules." %}
```text
apt-get install php7.2
apt-get install php-pear php7.2-curl php7.2-dev php7.2-gd php7.2-mbstring php7.2-zip php7.2-mysql php7.2-xml
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="5. Verify the installation." %}
```text
php -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

### Install Composer

Perform the following commands to install Composer:

{% code-tabs %}
{% code-tabs-item title="1. Download Composer and edit." %}
```text
wget https://getcomposer.org/composer.phar
mv composer.phar composer
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="2. Give permissions." %}
```text
chmod +x composer
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="3. Move the file to the local directory." %}
```text
mv composer /usr/local/bin
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="4. Verify the functionality." %}
```text
composer
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Install Node.js 10.13.0

Perform the following commands to install Node.js 10.13.0:

{% code-tabs %}
{% code-tabs-item title="1. Set \"Version\" and \"Distro\" variables." %}
```text
VERSION=v10.13.0
DISTRO=linux-x64
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="2. Download the program." %}
```text
cd /opt/
wget https://nodejs.org/download/release/v10.13.0/node-v10.13.0-linux-x64.tar.xz
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="3. Decompress the program." %}
```text
mkdir /usr/local/lib/nodejs
tar -xJvf node-$VERSION-$DISTRO.tar.xz -C /usr/local/lib/nodejs
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="4. Rename the directory." %}
```text
mv /usr/local/lib/nodejs/node-$VERSION-$DISTRO /usr/local/lib/nodejs/node-$VERSION
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="5. Configure the program." %}
```text
echo "VERSION=v10.13.0" >> ~/.bashrc
echo "DISTRO=linux-x64" >> ~/.bashrc
echo 'export NODEJS_HOME=/usr/local/lib/nodejs/node-$VERSION/bin' >> ~/.bashrc
echo 'export PATH=$NODEJS_HOME:$PATH' >> ~/.bashrc
. ~/.bashrc
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="6. Verify the installation." %}
```text
node -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Install ProcessMaker

Perform the following commands to install ProcessMaker 4 internal beta:

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="1. Install Git." %}
```text
apt-get install git
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

{% code-tabs %}
{% code-tabs-item title="2. Clone the project." %}
```text
git clone https://github.com/ProcessMaker/bpm.git
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="3. Enter the project." %}
```text
cd bpm/
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="4. Run Composer." %}
```text
composer install
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
Before you go to the next command, verify if npm is already installed:

{% code-tabs %}
{% code-tabs-item title="Verify if npm is already installed." %}
```text
npm -v
```
{% endcode-tabs-item %}
{% endcode-tabs %}

After you verify if npm is installed, do one of the following:

* **npm is not installed:** Continue to command 5 \(install the package manager\).
* **npm is installed:** Skip to command 6 \(run the manager inside the project\).
{% endhint %}

{% tabs %}
{% tab title="Debian / Kali / Mint / Ubuntu" %}
{% code-tabs %}
{% code-tabs-item title="5. Install the package manager." %}
```text
apt-get install npm@latest -g
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}
{% endtabs %}

{% code-tabs %}
{% code-tabs-item title="6. Run the manager inside the project." %}
```text
npm install
npm run dev
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="7. Edit the file." %}
```text
nano /etc/hosts
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% hint style="info" %}
You can change the IP address or the URL to one you prefer. But if you do so, you must make the change also in the `Homestead.yaml`file which is inside the project.
{% endhint %}

{% code-tabs %}
{% code-tabs-item title="8. Add the following line at the bottom of the file." %}
```text
192.168.10.10 bpm4.local.processmaker.com
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="9. Create a public key." %}
```text
ssh-keygen
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="10. Gets the server up." %}
```text
vagrant up
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="11. Enter the server." %}
```text
vagrant ssh
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="12. Go to the following path:" %}
```text
cd /home/vagrant/processmaker
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="13. Start the installation and ask for parameters." %}
```text
php artisan bpm:install
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Enter the following parameters:

* Specify `localhost` as your local database server.
* Specify `3306` as your local database port.
* Specify `workflow` as your local database name.
* Specify `homestead` as your local database username.
* Specify `secret` as your local database password.
* Specify `https://bpm4.local.processmaker.com` as your application URL.

{% hint style="info" %}
Alternatively, use the new URL that you assigned in the `hosts` and `Homestead.yaml` files.
{% endhint %}

## Log in to ProcessMaker

After ProcessMaker is installed, go to [https://bpm4.local.processmaker.com](https://bpm4.local.processmaker.com) or the new URL if you created one. Use the following credentials to [log in](../using-processmaker/log-in.md):

* Username: `admin`
* Password: `admin`

## Related Topics

{% page-ref page="prerequisites.md" %}

{% page-ref page="../using-processmaker/log-in.md" %}
