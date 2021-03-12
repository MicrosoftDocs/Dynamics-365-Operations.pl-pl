---
title: Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy
description: Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799011"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Umożliwienie użytkownikom otrzymywania wiadomości e-mail związanych z przepływem pracy

[!include [banner](../../includes/banner.md)]

Można skonfigurować system, aby wysyłał wiadomości e-mail do użytkowników w przypadku wystąpienia zdarzeń związanych z przepływem pracy. Na przykład, wiadomości e-mail mogą być wysyłane do użytkowników po przypisaniu do nich dokumentów do zatwierdzenia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.

1. Otwórz **Okienko nawigacji > Moduły > Administracja systemu > Użytkownicy > Użytkownicy**.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. W **Okienku akcji** kliknij **Opcje użytkownika**.
4. Kliknij kartę **Przepływ pracy**. Upewnij się, że sekcja **Powiadomienia** została rozwinięta. W sekcji **Powiadomienia** można określić sposób, w jaki użytkownik ma zostać powiadomiony o zdarzeniach związanych z przepływem pracy.  
5. W polu **Typ powiadomienia przepływu pracy dla pozycji w wierszu** wybierz opcję.
    - Zgrupowane — Powiadomienia dla towarów w wierszach są grupowane w jedną wiadomość e-mail.
    - Indywidualne — Wiadomość e-mail zostanie wysłana dla każdego towaru w wierszu.  
    - Jeśli chcesz, aby użytkownik otrzymywał powiadomienia w kliencie, zaznacz pole wyboru **Wysyłaj powiadomienia pocztą e-mail**.  
6. Kliknij przycisk **Zapisz**.
7. Zamknij stronę.

> [!NOTE]
> Szablony wiadomości e-mail przepływu pracy będą czerpane z szablonów wiadomości e-mail systemu lub szablonów wiadomości e-mail organizacji w zależności od tego, czy przepływ pracy jest przepływem pracy na poziomie systemu (nie dotyczący firmy), czy na poziomie organizacji (dotyczący firmy).
