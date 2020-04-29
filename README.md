# coba
echo 'deb https://download.jitsi.org stable/' | sudo tee /etc/apt/sources.list.d/jitsi-stable.list
wget -qO -  https://download.jitsi.org/jitsi-key.gpg.key | sudo apt-key add -
# Ensure support is available for apt repositories served via HTTPS
apt-get install apt-transport-https

# Retrieve the latest package versions across all repositories
apt-get update

# Perform jitsi-meet installation
apt-get -y install jitsi-meet

/usr/share/jitsi-meet/scripts/install-letsencrypt-cert.sh
