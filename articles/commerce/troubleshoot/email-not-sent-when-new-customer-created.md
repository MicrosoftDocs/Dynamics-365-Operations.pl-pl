---
title: Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349959"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Opis

Gdy nowy klient jest tworzony w centrali handlowej, powitalna wiadomość e-mail nie jest wysyłana do klienta, mimo że powiadomienie e-mail jest skonfigurowane dla typu powiadomienia e-mail **Utworzony przez klienta**.

## <a name="resolution"></a>Rozwiązanie

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Ustaw prawidłową wartość identyfikatora e-mail dla typu powiadomienia e-mail utworzonego przez klienta

Aby ustawić poprawną wartość **Identyfikatora wiadomości e-mail** dla typu powiadomienia e-mail **Utworzony przez klienta** w centrali, wykonaj następujące kroki.

1. Przejdź do **Handel detaliczny i inny \> Ustawienia Headquarters \> Handlowy profil powiadomień e-mail**.
1. W lewym okienku nawigacji wybierz profil powiadomień e-mail.
1. W sekcji **Ustawienia powiadomień o wydarzeniach w handlu detalicznym** dla typu powiadomienia e-mail **Utworzony przez klienta** ustaw pole **Identyfikator e-mail** na **NewCust**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie profilu powiadomienia](../email-notification-profiles.md)
