# Vibranium Shield

<img src="public/images/wg_logos/Logo-Large-Transparent.png"  width="180px" alt="Vibranium Shield logo" align="right">

Secure your online assets with Vibranium Shield - the ultimate web3 security browser extension. Our solution features advanced multi-layered security measures designed to protect against scams and fraud. This is done via proactive phishing protection and transaction analysis, providing you a comprehensive security suite.

<br>
<br>

# Detect and Block Malicious Websites

Vibranium Shield's Proactive Phishing Protection uses an ensemble of machine learning models to check for common phishing attack methods such as recently created domains, homoglyph translations and impersonation attempts.

<img src="https://cdn.walletguard.app/extension-assets/phishing-screen.png" alt="Phishing screen example">

<br>

# Transaction Simulations

What's the benefit of Transaction Simulations?
The blockchain can be scary without knowing what you're doing!

- Transaction Simulations will enable you to understand exactly what is entering and leaving your wallet on any transaction!
- This human readable context + a friendly UI will help defeat many scams we see in web3.
- Vibranium Shield's transaction simulation also works in tandem with our proactive phishing detection to provide deeper insights on transactions!
  <img src="https://cdn.walletguard.app/extension-assets/SimulationExample.gif" alt="Example of transaction simulation">

<br>

# How are we proxying transactions

Like MetaMask, Vibranium Shield injects the Ethereum web3 API into the JavaScript context of any website, enabling the secure reading and verification of transaction requests from decentralized applications (dApps).

Vibranium Shield acts as an intermediary between your browser and wallet, analyzing transactions without modification. Once you’ve made a decision, we return the transaction to your wallet without any changes, allowing Vibranium Shield to operate seamlessly in the background.

```typescript
  if (provider && !provider?.isWalletGuard) {
    log.debug({ provider }, 'Added proxy');

    try {
      Object.defineProperty(provider, 'request', {
        value: new Proxy(provider.request, requestHandler),
      });
      Object.defineProperty(provider, 'send', {
        value: new Proxy(provider.send, sendHandler),
      });
      Object.defineProperty(provider, 'sendAsync', {
        value: new Proxy(provider.sendAsync, sendAsyncHandler),
      });
      provider.isWalletGuard = true;
      console.log('Vibranium Shield is running!');
    } catch (error) {
      console.log('Vibranium Shield could not start!');
    }
  }
};

```

<br>

## Terms of Service and Privacy

💻 Open Source: We believe in product transparency. We encourage our users to audit our open-source codebase.

📄 Privacy: Your data privacy is very important to us. Check out our privacy policy here. https://walletguard.app/privacy

📋 Terms of service: By using Vibranium Shield you agree to our terms of use outlined here: https://walletguard.app/terms

<br>

## Contact Us

Any questions or concerns? contacts us!

- [Twitter](https://twitter.com/wallet_guard)
- [Discord](http://discord.gg/cM8USCesnd)
