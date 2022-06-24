---
title: Zarządzanie fakturami dla witryn sieci Web b2B e-commerce
description: W tym artykule opisano możliwości zarządzania fakturami Microsoft Dynamics 365 Commerce w witrynach sieci web handlu elektronicznego (B2B).
author: shajain
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: fa6b81187481a6b7f47ea02291e5a581052d6c7b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854933"
---
# <a name="invoice-management-for-b2b-e-commerce-websites"></a>Zarządzanie fakturami dla witryn sieci Web b2B e-commerce

[!include [banner](../../includes/banner.md)]

W tym artykule opisano możliwości zarządzania fakturami Microsoft Dynamics 365 Commerce w witrynach sieci web handlu elektronicznego (B2B).

Jest to typowe rozwiązanie dla firm, które obsługują transakcje B2B, aby akceptować zamówienia na kredyt odbiorcy, a następnie wysyłać faktury do odbiorców po zrealizowaniu zamówienia. Warunki płatności są zdefiniowane dla odbiorców i mogą wystąpić pewne rabaty, aby motywować odbiorców do zapłaty w terminie lub przed terminem. Aby zwiększyć prawdopodobieństwo terminowego otrzymania płatności, witryny sieci Web usług B2B e-commerce pozwalają klientom wyświetlić wszystkie ich faktury. Odbiorca może łatwo przefiltrować faktury, aby wyświetlać zapłacone, niezapłacone i częściowo zapłacone faktury wraz z terminami płatności.

![Strona faktur w witrynie B2B.](../media/ViewInvoices.png)

> [!NOTE]
> Zalogowany użytkownik może przeglądać i płacić tylko własne faktury. Jeśli konto organizacji jest skonfigurowane w menu rozwijaym **Konto płatnika** na skróconej karcie **Faktura i dostawa** rekordu odbiorcy w programie Commerce Headquarters, użytkownik będzie mógł wyświetlać i płacić faktury dla tego konta organizacji.

Na stronie **Faktury** w witrynie B2B użytkownik może wybrać niezapłaconą lub częściowo zapłaconą fakturę, a następnie wybrać pozycję **Płatność faktury**. Zaznaczona faktura zostanie dodana do koszyka i użytkownik może kontynuować płatność. Użytkownik może następnie zdecydować, czy zapłacić pełną kwotę faktury, czy tylko kwotę częściową. Użytkownik nie może korzystać z metody płatności na koncie do opłacania faktur.

> [!NOTE]
> Faktury można dodawać do koszyka tylko wtedy, gdy nie ma w nim aktualnie żadnych towarów. I odwrotnie, pozycje można dodawać do koszyka tylko wtedy, gdy nie ma w nim aktualnie żadnych faktur. Firma Microsoft planuje usunąć to ograniczenie w przyszłych wersjach usług Commerce.

![Strona koszyka w witrynie B2B.](../media/PayInvoice.png)

Na stronie **Faktury** użytkownik może także wybrać **pozycję Żądaj faktury** obok faktury. W ten sposób użytkownik może zażądać wysłania szczegółów faktury na ich zarejestrowany adres e-mail.

![Okno dialogowe żądania faktury.](../media/RequestInvoice2.png)

Gdy użytkownik zażąda faktury, żądanie zostanie przeniesione **do sekcji Żądania B2B** na **stronie Moje konto**. Następnie, po uruchomieniu zadań **P-0001** i **Synchronizuj zamówienia** oraz żądań kanału w centrali commerce, zostanie wywołana wiadomość e-mail o fakturze, a stan żądania B2B jest oznaczony jako ukończony.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
