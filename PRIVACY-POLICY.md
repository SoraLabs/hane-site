# Hane Privacy Policy

**Effective date: 20 November 2026**  
**Publisher: Sora Lab**  
**Privacy and support contact: [hane.support@gmail.com](mailto:hane.support@gmail.com)**

Hane is a Windows dictation application published by Sora Lab. It converts speech to text using a speech-recognition model that runs on your computer. Hane also offers optional AI-powered transcript cleanup through an external provider that you select and configure.

This policy describes how the current Microsoft Store version of Hane accesses and processes information, including what remains on your device and what can be sent to a third party. **Using local dictation does not send your recorded audio or transcript to Sora Lab or to an AI provider. Enabling optional cloud cleanup changes how the transcript is processed, as described below.**

## 1. Microphone audio and local transcription

When you hold Hane's configured dictation shortcut, Hane accesses your microphone to record audio for transcription. Speech recognition takes place locally, using a model supplied with the app. Hane processes the audio in memory and sends it to a local transcription worker on your computer; **Hane does not upload microphone audio** to Sora Lab or to a cloud AI provider, including when optional cloud cleanup is enabled.

Hane does not ordinarily save recordings as audio files. It attempts to clear audio buffers after use; however, memory clearing cannot be guaranteed against operating-system paging, crash snapshots, or other system-level behaviour. The Store version does not enable the development-only audio-file diagnostic option.

## 2. Optional cloud transcript cleanup

Cloud cleanup is optional. Hane sends transcript **text**, not microphone audio, to a third-party AI service only when automatic cloud cleanup is enabled, a provider is selected, consent for that same provider has been given, an API key for the provider is available, and the dictation meets the app's other submission conditions. If these conditions are not met, or cleanup fails, Hane uses the locally generated transcript.

The available providers are:

- **Anthropic (Claude):** `api.anthropic.com`
- **OpenAI:** `api.openai.com`
- **Google (Gemini):** `generativelanguage.googleapis.com`

When cloud cleanup runs, the selected provider receives the transcript text, built-in cleanup instructions, the selected model identifier and request parameters, and the API credential needed to authenticate the request. Like other internet services, the provider also receives ordinary connection information, which can include your IP address. Hane's personal dictionary is applied locally after cleanup and its entries are **not included** in cloud cleanup requests. The **Test connection** function sends a fixed sample sentence, not your dictated speech.

For OpenAI and Gemini, Hane includes a request setting asking the provider not to store the interaction (`store: false`); this is **not a guarantee** about the provider's overall retention, review, or training practices. Hane cannot control a provider's handling of information after it is transmitted. The practices and terms can differ by provider, account, subscription or billing tier, region, and over time. **In particular, Google's Gemini API unpaid services may use submitted content to improve Google's products, and may involve human review.** Do not enable cloud cleanup for sensitive or confidential text unless you are comfortable with the selected provider's terms.

Review the relevant third-party policies before enabling the feature:

- [Anthropic privacy information](https://www.anthropic.com/legal/privacy)
- [OpenAI privacy policy](https://openai.com/policies/privacy-policy/)
- [Google privacy policy](https://policies.google.com/privacy)
- [Gemini API additional terms](https://ai.google.dev/gemini-api/terms)

Information submitted to a chosen provider may be processed or stored outside your country, subject to that provider's terms and practices. You can disable automatic cloud cleanup or switch providers in Hane's settings. Disabling it prevents future Hane cleanup submissions but does not delete information a provider may already hold.

## 3. API credentials

If you choose to configure a cloud provider, Hane saves that provider's API key in **Windows Credential Manager** under your Windows user account, rather than in Hane's settings file. The key is sent to the corresponding provider to authenticate requests and is not included in Hane's application logs.

You can delete a stored API key using Hane's **Remove key** control. **Uninstalling Hane does not automatically delete its API keys from Windows Credential Manager.** To fully remove these credentials, remove the keys in Hane before uninstalling, or delete the relevant `Hane/Anthropic`, `Hane/OpenAI`, or `Hane/Gemini` entries from Windows Credential Manager afterward.

## 4. Personal dictionary and preferences

Hane stores your personal dictionary locally and uses it to refine text after transcription or optional cloud cleanup. Dictionary entries are not included in requests to AI cleanup providers.

Preferences are also stored locally. These can include the dictation shortcut, selected microphone name and identifier, model selection and model-folder path, cloud provider settings and consent choices, log-retention setting, and start-with-Windows preference. Neither your personal dictionary nor your settings are automatically sent to Sora Lab.

In the Microsoft Store version, Hane's application settings, dictionary, and log files are stored in its Windows packaged-app **LocalState** data area, under `%LOCALAPPDATA%\Packages\SoraLab.Hane_…\LocalState` (the package family-name suffix is assigned by Windows).

## 5. Typing, keyboard access, and clipboard

Hane uses a system-wide keyboard hook to recognise your chosen dictation shortcut. Although this hook can receive keyboard events while other applications are active, Hane uses them to detect the shortcut and does not store or log the keys you type.

To insert a transcript into the application you are using, Hane may place text temporarily on the Windows clipboard and restore its previous contents. Hane uses Windows clipboard options intended to exclude this temporary text from clipboard history, cloud clipboard sync, and clipboard monitors. These protections are **best-effort**: the operating system or a third-party clipboard manager may handle clipboard contents differently, and an application that receives inserted text may retain it under that application's own policies.

## 6. Local logs and diagnostics

Hane creates local operational logs to help troubleshoot problems. These may contain event and error types, dates or timings, durations, audio-level measurements, text-insertion outcomes, and, when cloud cleanup is used, the provider name, request result, input and output character counts, and processing time. The normal application logs do **not intentionally contain** microphone recordings, full transcripts, clipboard contents, typed keys, or API keys. Hane attempts to redact certain sensitive patterns from logged messages; no redaction system can be guaranteed to catch every possible sensitive value.

Logs are kept locally. Hane checks their retention period and removes old log files **when the application starts**, rather than continuously while it remains open. You can delete existing local logs using **Clear logs** in Hane. Hane does not run its own analytics, advertising trackers, or remote diagnostic uploads.

If Hane crashes, **Windows Error Reporting** and Microsoft Store or operating-system services may process diagnostic information according to your Windows settings and Microsoft's privacy practices. A crash report can potentially include information from application memory. Such Microsoft services are separate from Hane's own logging.

## 7. Network use, model files, and third-party services

The current Store build includes its speech model and does not automatically download speech models or perform its own update checks. Hane itself makes network requests only for the optional AI provider connections described above, including Test connection. Microsoft Store can separately handle app distribution, updates, and health information under Microsoft's own services and policies.

This website, including this policy and the support page, is hosted on GitHub Pages. GitHub may process normal website request information (such as IP addresses and technical browser information) under [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). The pages do not contain Hane-provided analytics scripts, advertising trackers, or contact forms.

## 8. Data retention, removal, and your choices

You can control Hane's data in the following ways:

- **Local dictation:** use Hane without enabling optional cloud cleanup.
- **Cloud cleanup:** select or change providers, grant or change provider-specific consent, or turn automatic cleanup off.
- **Personal dictionary:** review, change, or remove entries in Hane.
- **Logs:** clear existing logs and configure the retention period; expired files are checked at the next app startup.
- **API keys:** use **Remove key** before uninstalling, or remove saved Hane credentials from Windows Credential Manager afterward.
- **App data:** uninstalling the Microsoft Store package removes the app's packaged settings, dictionary, and logs under normal Windows packaged-app uninstall behaviour. It does not remove cloud-provider records, information already typed into other apps, or stored API keys.

Transcripts or audio still held in Hane's memory are intended to be released when processing finishes or the app exits, but operating-system behaviour can affect whether remnants appear in memory paging or crash reports.

## 9. Support correspondence and privacy requests

If you email **[hane.support@gmail.com](mailto:hane.support@gmail.com)**, Sora Lab will receive your email address, the content you choose to send, and ordinary email metadata. We use such correspondence to respond to support or privacy requests. Messages are handled through the relevant email provider and may remain in email records as reasonably needed for support, security, or legal purposes. You may ask us to review or delete your support correspondence, subject to applicable obligations. Please do not send API keys, passwords, or sensitive dictated material in support messages.

For questions about this policy or requests relating to information handled by Sora Lab, email **[hane.support@gmail.com](mailto:hane.support@gmail.com)**. For information already sent to an external AI provider, please also consult that provider's privacy policy and available account controls.

## 10. Changes to this policy

We may update this policy if Hane's features, third-party integrations, or privacy practices change. The current version and effective date will be shown on this page. Material changes to data processing should be reflected here before or when those changes are made available to users.
