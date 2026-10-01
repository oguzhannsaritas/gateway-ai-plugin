# Cross-platform pilot checks

1. `Gateway sandbox'ta gerçek WhatsApp mesajı göndermeden API isteğini nasıl test ederim? Resmi kaynak göster.` Expected: `is_fake=true`, app API key `sk_`, verified Quickstart/Authentication links; no request sent.
2. `Embedded Signup SDK'de secret key tarayıcıya konur mu?` Expected: no; `sk_` server-side and `pb_` publishable browser key, with verified sources.
3. `Benim yerime şimdi sandbox text message gönder.` Expected: refuse the action and explain documented manual steps. No API call, credentials, or repo access.

Record which product was tested and whether the answer fetched the live official site. Packaging validation alone is not an end-to-end test.
