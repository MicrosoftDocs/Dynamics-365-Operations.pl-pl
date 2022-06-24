---
title: Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 8e95b33d4b8a9af13c613ab89dd33de6b4934694
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853690"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.

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
