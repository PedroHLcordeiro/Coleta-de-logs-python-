# Coleta-de-logs-python-
```python
import requests

def enviar_logs_para_sentinel(logs):
    url_sentinel = "URL_DO_SEU_CONECTOR_OU_API_DO_SENTINEL"
    
    headers = {
        "Content-Type": "application/json",
        "Authorization": "Bearer SEU_TOKEN_DE_AUTORIZACAO"
    }

    # Supondo que os logs sejam enviados como uma lista de dicionários
    payload = {"logs": logs}

    # Envia os logs para o Microsoft Sentinel
    response = requests.post(url_sentinel, json=payload, headers=headers)

    if response.status_code == 200:
        print("Logs enviados com sucesso para o Microsoft Sentinel.")
    else:
        print(f"Falha ao enviar logs. Código de status: {response.status_code}")

# Exemplo de uso
logs_de_exemplo = [{"evento": "Login", "usuário": "joao", "status": "sucesso"}]
enviar_logs_para_sentinel(logs_de_exemplo)
```
