# OTP

Практический результат

Если строить аудит защищенности почтового сервиса и Web Proxy по ISO/IEC 27001:2022, то наиболее релевантными будут 23 меры контроля:

Организационные: 5.7, 5.12, 5.14–5.24, 5.30, 5.34, 5.37.

Технологические: 8.5, 8.7–8.9, 8.12, 8.15, 8.16, 8.20, 8.21, 8.23, 8.24.

Для практики Application Security и Security Architecture из этого стандарта можно сформировать единый аудит-чеклист примерно из 100–150 проверок отдельно для:

Почтового сервиса (Email Security Gateway/M365/Exchange).
Web Proxy/Secure Web Gateway.
Общих организационных процессов управления этими сервисами по ISO 27001.

https://pqm-online.com/assets/files/pubs/translations/std/iso-mek-27001-2022.pdf

A.5.7 Threat Intelligence

Очень актуально.

Для email:

✓ обновление IOC;

✓ RBL;

✓ anti-spam feeds;

✓ phishing feeds.

Для Web:

✓ URL reputation;

✓ malware feeds;

✓ DNS reputation;

✓ IP reputation.

A.5.12 Классификация информации

Почтовый сервис:

Confidential;
Internal;
Public.

Web Proxy:

контроль доступа к чувствительным данным;
DLP.

A.5.14 Передача информации

Практически полностью относится к почте.

Проверяется наличие:

TLS;
SMTPS;
STARTTLS;
S/MIME;
PGP;
защищенных каналов передачи файлов;
правил обмена информацией.

A.5.15 Управление доступом

Для Email:

MFA;
RBAC;
администраторские роли;
shared mailbox.

Для Proxy:

авторизация пользователей;
групповые политики;
административный доступ.

A.5.16–5.18 Identity & Access

Проверяется:

жизненный цикл учетных записей;
управление паролями;
MFA;
отзыв доступа;
PAM;
сервисные аккаунты.

A.5.19–5.23 Поставщики

Если используются:

Microsoft 365;
Proofpoint;
Mimecast;
Cisco Umbrella;
Zscaler;
Cloudflare Gateway;

необходимо:

SLA;
security requirements;
контроль изменений;
аудит поставщика.

A.5.24–5.28 Incident Management

Для почты:

phishing;
malware;
account compromise.

Для Proxy:

C2;
TOR;
botnet;
DNS tunneling.

Проверяется:

процедуры;
расследования;
сохранение доказательств;
lessons learned.

A.5.30 Business Continuity

Для Email:

DR;
резервные MX;
backup mailbox.

Для Proxy:

HA;
кластер;
резервные каналы;
failover.

A.5.34 Privacy

Особенно важно.

Проверяется:

защита персональных данных;
контроль обработки;
журналирование;
минимизация хранения.

A.5.37 Документированные процедуры

Должны существовать:

Для Email:

создание mailbox;
удаление;
quarantine;
incident response;
spam handling.

Для Proxy:

whitelist;
blacklist;
SSL inspection;
bypass;
emergency rules.

Технологические меры (раздел 8)

Это наиболее практичные пункты для технического аудита.

A.8.5 Безопасная аутентификация

Проверить:

MFA;
Conditional Access;
OAuth;
Legacy Authentication disable.

A.8.7 Malware Protection

Email:

AV;
sandbox;
attachment scanning.

Web:

malware scanning;
download inspection.

A.8.8 Vulnerability Management

Проверить:

обновления Proxy;
обновления почтового шлюза;
CVE management;
hardening.

A.8.9 Configuration Management

Для аудита очень важно.

Проверяется:

baseline;
backup config;
version control;
change management.

A.8.12 Data Leakage Prevention

Email:

DLP policies;
блокировка вложений;
шифрование.

Web:

upload control;
cloud storage;
clipboard;
file transfer.

A.8.15 Logging

Для Email:

SMTP;
admin actions;
mailbox audit;
transport rules.

Для Proxy:

URL;
DNS;
SSL;
uploads;
downloads.

Проверяется защита и хранение логов.

A.8.16 Monitoring

Необходимо наличие:

SIEM;
SOC;
UEBA;
alerting;
IOC detection.

A.8.20 Network Security

Проверяется:

сегментация;
firewall;
DMZ;
reverse proxy;
WAF (если применимо).

A.8.21 Network Services

Для Email:

SMTP;
IMAPS;
POP3S;
MAPI;
ActiveSync.

Для Proxy:

HTTP;
HTTPS;
SOCKS;
PAC;
Explicit/Transparent mode.

A.8.23 Web Filtering

Это прямое требование для Web Proxy:

доступ к внешним веб-сайтам должен находиться под управлением для снижения воздействия вредоносного содержимого.

Проверяется:

URL filtering;
Category filtering;
Safe Search;
HTTPS inspection;
block pages;
malware sites;
phishing sites.

A.8.24 Cryptography

Для Email:

TLS;
S/MIME;
DKIM.

Для Proxy:

TLS inspection;
certificate management;
key management.
