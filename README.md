# teamblockchain-agentic-mvp

Copy of the LDE Wallet AI session host, seated on TeamBlockchain Limited (`teamblockchain.net`).

Emulated agentic session host for Jonny Fry as CEO of TeamBlockchain Limited. Signs LDI presence with `JONNY_DEVICE_PRIVATE_KEY_PEM`. Not a real HSM. Do not commit the PEM.

Public host: `https://agentic.teamblockchain.net`

Device: e78c8cdf81b599cfc1a7488154536074ffd8aafcfebc8b519a9aa84839bd392e

The agent still interrogates the live LDI oracle and LDEDI receipts. Those are the control plane. This repo is the TeamBlockchain session face.

Vercel env:
- JONNY_DEVICE_PRIVATE_KEY_PEM
- JONNY_DEVICE_ID=e78c8cdf81b599cfc1a7488154536074ffd8aafcfebc8b519a9aa84839bd392e
- LDI_ORACLE_URL=https://www.londonagentic.ai
- DATABASE_URL
- JONNY_XAI_API_KEY
- JONNY_XAI_MODEL=grok-4

After deploy:

```bash
curl -sS -X POST https://agentic.teamblockchain.net/api/v1/presence -H 'content-type: application/json' -d '{"state":"present"}'
curl -sS "https://www.londonagentic.ai/api/v1/cover?device_id=e78c8cdf81b599cfc1a7488154536074ffd8aafcfebc8b519a9aa84839bd392e"
```

Session:

`https://agentic.teamblockchain.net/session/{key_id}`
