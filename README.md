<!DOCTYPE html>
<html>
<head>
  <title>Jarvis Always‑On</title>
</head>
<body style="text-align:center; font-family:sans-serif">
  <h1>🪄 Jarvis (24/7 in browser)</h1>
  <p>Status: <span id="status">Connecting...</span></p>

  <script src="https://cdn.retellai.com/retell-sdk.js"></script>
  <script>
    const RETELL_API_KEY = "key_32ff3ad489f734c56514f9010ecc";
    const AGENT_ID = "agent_f5330dd54d35e2ad3ec55bf7f5";

    Retell.init({
      apiKey: RETELL_API_KEY,
      agentId: AGENT_ID
    });

    Retell.onReady(() => {
      document.getElementById("status").innerText = "Connected. Say 'Wake up, Jarvis' to talk.";
      Retell.startCall();
    });

    Retell.onError((err) => {
      document.getElementById("status").innerText = "Error: " + err.message;
    });
  </script>
</body>
</html>

