---
title: Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy
description: Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560505"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy. Na przykład, wiadomości e-mail mogą być wysyłane do użytkowników po przypisaniu do nich dokumentów do zatwierdzenia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Kliknij opcję Opcje użytkownika.
4. Kliknij kartę Przepływ pracy.
    * Upewnij się, że jest rozwinięta sekcja Powiadomienia.     W sekcji Powiadomienia można określić sposób, w jaki użytkownik ma zostać powiadomiony o zdarzeniach związanych z przepływem pracy.  
5. W polu Typ powiadomienia przepływu pracy dla pozycji w wierszu wybierz opcję.
    * Zgrupowane — Powiadomienia dla towarów w wierszach są grupowane w jedną wiadomość e-mail.    Indywidualne — Wiadomość e-mail zostanie wysłana dla każdego towaru w wierszu.  
    * Jeśli chcesz, aby użytkownik otrzymywał powiadomienia na kliencie, zaznacz pole wyboru Wysyłaj powiadomienia pocztą e-mail.  
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

