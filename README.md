<p align="center">
    <a href="https://sublimesecurity.com"><img src="https://user-images.githubusercontent.com/11003450/102955006-e908f080-44a2-11eb-8de6-d6f8a712cb90.png" width="75%" alt="Sublime Logo" /></a>
</p>

<p align="center">
  <h3 align="center">A Customizable Email Security Platform for the Modern Security or IT Team</h3>
</p>

<p align="center">
  <a href="https://dev.docs.sublimesecurity.com/docs/quickstart">Quick Start</a> |
  <a href="https://dev.docs.sublimesecurity.com">Documentation</a> |
  <a href="https://blog.sublimesecurity.com">Blog</a> |
  <a href="https://angel.co/company/sublime-security/jobs" alt="Sublime on Notion">Careers</a> |
</p>

<p align="center">
  Sublime is a platform for detecting and remediating threats in your email environment, configuring compliance policies, and identifying and reducing risk.
</p>

## Use Cases

Security and IT teams can use Sublime for:
|         Use Case         | Description                                                                               |
| :----------------------: | ----------------------------------------------------------------------------------------- |


## Usage

Follow our [Quick Start Guide](https://docs.sublimesecurity.com/quick-start) to use Sublime in a matter of minutes!

Sublime uses [Message Query Language (MQL)](https://dev.docs.sublimesecurity.com/docs/message-query-language) for analysis, and each deployment is pre-installed with [100+ open source detection rules](https://github.com/sublime-security/sublime-rules).

Use our [Tutorials](https://dev.docs.sublimesecurity.com/docs/tutorials) to learn about the Sublime system, data ingestion, and writing your own rules.

## Email Message Analysis

Sublime uses [Message Query Language (MQL) rules](https://dev.docs.sublimesecurity.com/docs/message-query-language) to analyze email messages from various mail sources.

### Community API

The Community API is a free API for analyzing messages using MQL. Bring Your Own Messages. Use cases:
- Triage reported phish

The example below can be used with the API to identify employee impersonation phishing attacks:
```javascript
type.inbound
and sender.display_name in ('first_name1 last_name1', 'first_name2 last_name2', 'first_name3 last_name3')
and sender.email.domain.domain != '{your_domain_1}'
```

### Sublime Platform
_Coming soon_
Use live-flow email connectors for Office 365, G Suite, and IMAP and a pretty Dashboard.

The example below can be used with the Platform to identify employee impersonation phishing attacks:
```javascript
type.inbound
and contains(sender.display_name, org.display_names)
and sender.email.domain.root_domain != org.domains[].root_domain
and org.count_to_sender_domain == '0'
```

If this rule returns `true`, a pre-configured action will execute, such as an alert to your SIEM, auto-trash from the user's mailbox, or the insertion of a warning banner.
