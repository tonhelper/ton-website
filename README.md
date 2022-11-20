# ton-website
This guide explains how to run a Website on The Open Network.
You can run a web server with your website and make it available on the TON Network. This is called TON Site.
To access TON Site you will need connections through TON-proxy.
Follow the guide below and you will launch your first TON Site.

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
  
  </li>
  <li></li>
  <li></li>
</ol>
