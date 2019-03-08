---
title: Powiadomienia o alertach klienta wysyłane pocztą e-mail
description: Ten temat zawiera informacje dotyczące sposobu konfigurowania reguł wysyłania pocztą e-mail powiadomień o wystąpieniu zdefiniowanych zdarzeń.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 314f04eec04a75aed058c9c38066738e8758f653
ms.sourcegitcommit: 440ebe14ad26574ba227d23ee8370f6b6110645b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/01/2019
ms.locfileid: "373813"
---
# <a name="client-alert-notifications-by-email"></a>Powiadomienia o alertach klienta wysyłane pocztą e-mail

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

W Microsoft Dynamics 365 for Finance and Operations można zdefiniować niestandardowe reguły alertów umożliwiające monitorowanie filtrowanych widoków danych i automatyczne wysyłanie powiadomień pocztą e-mail po wystąpieniu zdarzeń wstępnie zdefiniowanych. Opcja wysyłania powiadomień pocztą e-mail jest dostępna dla wszystkich obsługiwanych typów alertów i można już również włączyć dla istniejących reguł alertów.

Można używać wbudowanych formantów do tworzenia reguł alertów monitorujących przefiltrowane widoki zadań wsadowych systemu. Monitorowanie wartości pola **Stan** pozwala również skonfigurować reguły alertów, które wysyłają wiadomość e-mail, kiedy zadanie wsadowe nie powiedzie się. Po utworzeniu tych reguł alertów nie trzeba już sprawdzać raportów dotyczących zmian danych biznesowych. Zamiast tego można zlecić monitorowanie usłudze inteligentnego wykrywania zmian w Finance and Operations.

Alerty klienta zależą od podsystemu e-mail dostarczonego za pośrednictwem integracji z Microsoft Office. Zaleca się korzystanie z usług dostawcy protokołu SMTP (Simple Mail Transfer Protocol), dzięki czemu dystrybucja wiadomości e-mail nie musi opierać się na lokalnym kliencie poczty.

Aby wysłać powiadomienia pocztą e-mail, należy skonfigurować usługi zintegrowanych wiadomości e-mail. Powiadomienia e-mail są wysyłane do adresatów w imieniu właścicieli alertów.

Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail w Finance and Operations, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../organization-administration/configure-email.md).

Poniższy obraz przedstawia okno dialogowe **Utwórz regułę alertu**, które teraz zawiera opcję **Wyślij wiadomość e-mail**.

[![Okno dialogowe Utwórz regułę alertu z opcją Wyślij wiadomość e-mail ustawioną na wartość Tak](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Gdy opcja **Wyślij wiadomość e-mail** ma wartość **Tak**, powiadomienia o alertach będą nadal dostarczane z Centrum akcji.

## <a name="alert-notification-email-templates"></a>Szablony wiadomości e-mail z powiadomieniem o alercie

Usługa wysyła powiadomienia e-mail przy użyciu wstępnie zdefiniowanych szablonów wiadomości e-mail zawierających podstawowe informacje powiadomienia o alercie. Te informacje zawierają bezpośrednie łącze do strony, na której zdefiniowano regułę alertu.

Poniższa ilustracja pokazuje strukturę powiadomień o alertach po ich odebraniu pocztą e-mail.

[![Powiadomienia o alertach oparte na szablonach i służące do rejestrowania tworzenia, zmian pól i wykrywania szablonów](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)
