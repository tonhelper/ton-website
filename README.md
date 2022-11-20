# ton-website
This guide explains how to run a Website on The Open Network.<br>
You can run a web server with your website and make it available on the TON Network. This is called TON Site.<br>
To access TON Site you will need connections through TON-proxy.<br>
Follow the guide below and you will launch your first TON Site.<br>

<ol>
  <li>Rent or boot up your server on an Ubuntu experience (preferably 22.04 and at least 4GB of RAM).</li>
  <li>Connect to the server via SSH.</li>
  <li>Clone the following repository with git clone.
    <ol>
      <strong>git clone https://github.com/tonhelper/ton-website.git</strong>
    </ol>
  </li>
  <li>Go to ton-site folder
    <ol>
      <strong>cd ton-site</strong>
    </ol>
  </li>
  <li>All scripts must be made executable with the following commands.
    <ol>
      <strong>chmod +x ./install_packets_for_rldp_proxy.sh</strong>
    </ol>
    <ol>
      <strong>chmod +x ./generate_adnl.sh</strong>
    </ol>
    <ol>
      <strong>chmod +x ./run_rldp_proxy.sh</strong>
    </ol>
  </li>
  <li>
Run the script to download and build everything you need (lite-client, func, fift, tonlib-cli, rldp-http-proxy, generate-random-id). This may take a long time. Better follow the process so that everything is installed correctly.
    <ol>
      <strong>./install_packets_for_rldp_proxy.sh</strong>
    </ol>
  </li>
  <li>To generate private key and adnl run the following script:
    <ol>
      <strong>./generate_adnl.sh</strong>
    </ol>
  </li>
  <li>After executing the script in the terminal, you will get two long lines. They will be separated by a space.
    <ol>
      For example: <strong>AD77FB007A10429920E4AE2BEAF2844E8A76074E25B46AAEBDD5AC57373B26B0  wwxp6yapiiefgja4sxcx2xsqrhiu5qhjys3i2voxxk2yvzxhmtlalt2</strong>
    </ol>
    The first one is <strong>Private Key</strong> and the second one is <strong>adnl</strong>. Write them down for yourself. The Private Key must be written when adding to the TON-site line if you want to link the domain to the site on dns.ton.org!
  </li>
  <li>Now, in order to raise your proxy server, run the last script. After starting, you will be asked to enter your server ip address and adnl, which you received in the last step.
      <ol>
      <strong>./run_rldp_proxy.sh</strong>
    </ol>
  </li>
  <li>Your proxy server is running and you can test its operation. To do this, you need to enable the proxy in your browser or operating system settings. Specify the <strong>IP of your server and port 8080</strong> as the host. If you did everything correctly, test it by going to the site <strong>http://makemoney.ton</strong></li>
  <li>Now let's test your site. To do this, copy our adnl and make the following request in the address bar:
    <ol>
      For Example: <strong>http://wwxp6yapiiefgja4sxcx2xsqrhiu5qhjys3i2voxxk2yvzxhmtlalt2</strong>
    </ol>
      Without an attached domain, this may not work quite correctly, but theoretically, the site should open for you.
  </li>
  <li>Bind DNS domain to adnl address:
      <ul>
      <li>Win an auction for a domain name at https://dns.ton.org</li>
      <li>Enter your domain address</li>
      <li>Сonnect the official TON Wallet extension to the browser</li>
      <li>Click edit</li>
      <li>In the TON-site field, enter your key (private key), which was obtained when executing the ./generate_adnl.sh command</li>
      </ul>
    Congratulations! You now have your website on the TON network.
  </li>
  <li>Also, if you connect via ssh, then after disconnecting the session will be interrupted along with the proxy. To avoid this, install screen with the following command:
      <ul>
      <li><strong>sudo apt install screen</strong></li>
      <li><strong>screen -R ton_proxy</strong></li>
      <li><strong>bash run_rldp_proxy.sh</strong></li>
      </ul>
    Close the terminal without interrupting the proxy.
  </li>
  <li>Now your site will continue to work even if you close the terminal. In order to publish something else instead of the welcome page, refer to the settings of the Nginx web server. If you want to leave this page to replace the wallet details with your own - edit the JS const "wallet" and replace the image with the QR code.</li>
  <br>
  <li></li>
</ol>
