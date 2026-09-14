# Security policy and review status
Updated September 14, 2026.

This project has developer-prepared documentation and tests, not an independent security assessment or institutional approval. Windows 2.0 is unsigned. Follow your institution's decision before using sensitive, confidential, or regulated documents.

## Reporting
Contact Page Durham / LearnAIID privately through your existing project or institutional contact. Provide the affected version, platform and a synthetic reproduction. Do not post real documents, credentials or exploit details in public issues. A dedicated response address and response-time agreement have not yet been established.

## Processing and limits
Browser document processing runs in the tab; sampled tests observed no document uploads or persistent document storage. The browser downloads app/model/language resources and has network access. Hosting logs and platform code, extensions, OS memory and exported files need separate assessment. Model/OCR application caching is disabled; older claims of a one-time persistent model cache are obsolete.

Windows 2.0's guided workspace uses bundled assets, a sandboxed renderer, a nonpersistent session and blocked external renderer requests. The native helper and Microsoft Office conversion are separate processes; Office/OS temporary files and network behavior are outside those renderer controls.

Optional Anthropic cloud-AI modes exist in the developer Python CLI and can transmit document imagery when invoked with credentials. They are excluded from the distributed native helper and are distinct from offline guided AI.

No guarantee of secure erasure, malicious-content removal, zero vulnerabilities, antivirus acceptance or universal document accessibility is made. Exports inherit destination-folder, backup and sync policies.

## Source and assessment
The full browser and Windows source repositories are private and available to invited reviewers. The tool uses open-source components; the complete application is not publicly open source. Notices accompany the Windows package.

- [Browser review package](https://github.com/BelovedCoachP/pixel-perfect-clone-31624-c9233ca7/tree/security-review-2026-09-14/docs/security)
- [Windows review package](https://github.com/BelovedCoachP/pdf-remediator/tree/security-review-2026-09-14/docs/security)
- [Released versions](https://pdf-remediate.lovable.app/updates)

The September 14 scans identified advisories in the September 10 dependency snapshots. Browser v1.26.1 and rebuilt Windows 2.0.1 contain tested dependency fixes. Evidence is in the review package; existing Windows 2.0 installations must be replaced to receive these fixes. See the evidence and risk register for exact scope.

Release checksums verify integrity against a published value; they do not replace publisher signing. Do not bypass institutional installation restrictions. Windows 2.0 has no automatic updater.

