# meu-ansible

Playbooks consumidos pelo AWX para automações do Aegis e do Sentinel AIOps.

## Sentinel AIOps

- `playbooks/sentinel_windows_health.yml`: coleta uptime, memória, discos e estado
  de serviços sem modificar o host.
- `playbooks/sentinel_restart_windows_service.yml`: reinicia somente serviços da
  allowlist e exige a variável `service_name`. O modo check pode ser usado para
  validar a seleção sem reiniciar o serviço.
- `playbooks/sentinel_configure_zabbix_agent.yml`: adiciona o Zabbix Server à
  allowlist do agente Windows, cria backup e reinicia somente o agente.

Os templates do Sentinel devem exigir `limit` no lançamento para impedir a
execução acidental em todo o inventário.
