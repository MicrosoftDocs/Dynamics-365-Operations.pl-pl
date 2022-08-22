---
title: Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219412"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>Powitalna wiadomość e-mail nie jest wysyłana po utworzeniu nowych klientów

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w przypadku niesyłania powiadomienia pocztą e-mail powitaną po utworzeniu nowego odbiorcy w programie Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Opis

Gdy nowy klient jest tworzony w centrali handlowej, powitalna wiadomość e-mail nie jest wysyłana do klienta, mimo że powiadomienie e-mail jest skonfigurowane dla typu powiadomienia e-mail **Utworzony przez klienta**.

## <a name="resolution"></a>Rozwiązanie

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Skojarz profil powiadomienia pocztą e-mail w obszarze Parametry handlu

1. W centrali rozwiązania przejdź do opcji **Retail i Commerce \> Ustawienia centrali \> Parametry \> Parametry rozwiązania Commerce \> Ogólne**.
2. Z listy rozwijanej **Profil powiadomień pocztą e-mail** wybierz profil powiadomień e-mail, który zawiera mapowanie między typem powiadomienia utworzonego przez klienta a szablonem wiadomości e-mail utworzonym przez klienta.  

> [!NOTE] 
> Gdy włączysz powiadomienia utworzone przez klienta, klienci utworzeni we wszystkich kanałach w ramach podmiotu prawnego otrzymają wiadomość e-mail utworzoną przez klienta. Obecnie powiadomienia tworzone przez klientów nie mogą być ograniczone do jednego kanału.

Aby uzyskać więcej informacji, zobacz temat [Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie profilu powiadomienia](../email-notification-profiles.md)
