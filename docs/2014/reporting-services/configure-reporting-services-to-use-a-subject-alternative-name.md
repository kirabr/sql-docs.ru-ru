---
title: Настройка использования альтернативного имени субъекта Reporting Services | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
caps.latest.revision: 4
author: maggiesmsft
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 2890cea5f4c39d27ce89d4d9c5bcc3efe7384039
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37284790"
---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a>Настройка Reporting Services для использования альтернативного имени субъекта
  В этом разделе объясняется, как настроить [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] (SSRS), чтобы использовать альтернативное имя субъекта (SAN), изменив файл rsreportserver.config и используя средство Netsh.exe.  
  
||  
|-|  
|**[!INCLUDE[applies](../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в основном режиме|  
  
 Инструкции применяются к URL-адресу службы отчетов, а также URL-адресу веб-службы.  
  
 Чтобы использовать SAN, SSL-сертификат должен быть зарегистрирован на сервере, подписан и иметь закрытый ключ. Самозаверяющий сертификат использовать невозможно.  
  
 URL-адреса в [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] могут быть настроены для использования SSL-сертификат. Обычно сертификат имеет только имя субъекта, которое позволяет ему использовать только один URL-адрес для сеанса SSL. SAN — это дополнительное поле в сертификате, которое позволяет службе SSL прослушивать и быть допустимой для многих URL-адресов, а также совместно использовать порт SSL с другими приложениями. SAN выглядит следующим образом: www.s2.com.  
  
 Дополнительные сведения о параметрах SSL для [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], см. в разделе [Настройка подключений SSL на сервер отчетов в собственном режиме](security/configure-ssl-connections-on-a-native-mode-report-server.md).  
  
### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a>Настройка SSRS для использования альтернативного имени субъекта для URL-адреса веб-службы  
  
1.  Запустите диспетчер конфигурации служб Reporting Services.  
  
     Дополнительные сведения см. в разделе [Использование диспетчера конфигурации служб Reporting Services (собственный режим)](../sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
2.  Выберите на странице **URL-адрес веб-службы** порт SSL и SSL-сертификат.  
  
     ![Диспетчер конфигурации служб Reporting Services](media/reportingservices-configurationmanager.png "Диспетчер конфигурации служб Reporting Services")  
  
     Диспетчер конфигурации зарегистрирует SSL-сертификат для порта.  
  
3.  Откройте файл rsreportserver.config.  
  
     Файл для служб SSRS в собственном режиме находится в следующей папке по умолчанию.  
  
    ```  
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer  
    ```  
  
4.  Скопируйте раздел URL-адреса для приложения веб-службы сервера отчетов.  
  
     Например, далее указан исходный раздел URL-адреса.  
  
    ```  
        <URL>  
         <UrlString>https://localhost:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
  
    ```  
  
     Ниже указан измененный раздел URL-адреса.  
  
    ```  
    <URL>  
         <UrlString>https://www.s1.com:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
        <URL>  
         <UrlString>https://www.s2.com:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
  
    ```  
  
5.  Сохраните файл rsreportserver.config.  
  
6.  Откройте командную строку от имени администратора и запустите средство Netsh.exe.  
  
    ```  
    C:\windows\system32\netsh  
    ```  
  
7.  Переключитесь в контекст HTTP, введя следующее.  
  
    ```  
    Netsh>http  
    ```  
  
8.  Отобразите существующие urlacl, введя следующее.  
  
    ```  
    Netsh http>show urlacl  
    ```  
  
     Появится запись, аналогичная следующей.  
  
    ```  
    Reserved URL            : https:// www.s1.com:443/ReportServer/  
        User: NT SERVICE\ReportServer  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)  
    ```  
  
     urlacl — это DACL (список управления доступом на уровне пользователей) для зарезервированного URL-адреса.  
  
9. Создайте альтернативное имя субъекта с тем же пользователем и SDDL как существующую запись, введя следующее.  
  
    ```  
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer    
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)  
  
    ```  
  
10. Щелкните на странице **Состояние сервера отчетов** диспетчера конфигурации Reporting Services кнопку **Остановить** , а затем нажмите **Запустить** , чтобы перезапустить сервер отчетов.  
  
## <a name="see-also"></a>См. также  
 [Файл конфигурации RSReportServer](report-server/rsreportserver-config-configuration-file.md)   
 [Диспетчер конфигурации служб Reporting Services &#40;собственный режим&#41;](../sql-server/install/reporting-services-configuration-manager-native-mode.md)   
 [Изменение файла конфигурации служб Reporting Services (RSreportserver.config)](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)   
 [Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)](install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
