---
title: Problemy z Troubleshoot Dynamics 365 Payment Connector dla Adyen
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w uzyskania pomocy technicznej w przypadku problemów z łącznikiem płatności Microsoft Dynamics 365 dla Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 687f2fdff5e29cc25fae911b015164f0d90aee88
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268873"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Problemy z Troubleshoot Dynamics 365 Payment Connector dla Adyen

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w uzyskania pomocy technicznej w przypadku problemów z łącznikiem płatności Microsoft Dynamics 365 dla Adyen.

## <a name="description"></a>opis

Masz problemy z łącznikiem płatności Dynamics 365 dla Adyen w następujących obszarach, a musisz uzyskać pomoc od zespołu Adyen:

- Konfiguracja punktu sprzedaży (POS), nowoczesnego punktu sprzedaży (MPOS), centrum obsługi lub Dynamics 365 Commerce
- Numer odwołania dostawcy usług płatności Adyen (NA PRZYKŁAD: jeśli użytkownik ma pytania dotyczące odmów, w tym ręcznego wprowadzania klawisza \[MKE\])
- Wszystko, co nie działa w środowisku handlowym testowym lub na żywo

## <a name="resolution"></a>Rozdzielczość

Użyj poniższego szablonu wiadomości e-mail, aby rozpocząć proces pomocy technicznej z zespołem Adyen. Aby przyspieszyć rozwiązywanie problemów, upewnij się, że wiadomość e-mail zawiera wszystkie wymagane szczegóły.

| Pole        | Wartość |
|--------------|-------|
| do           | `support@adyen.com` |
| DW           | |
| Wiersz tematu | Żądanie pomocy technicznej Microsoft Dynamics |
| Treść         | <p>Dzień dobry przedstawicielu pomocy technicznej.</p><p>Proszę podać pomoc techniczną dla następującego problemu:</p><ul><li>Konto handlowca</li><li>Środowisko (Test/Prod)</li><li>Kanał sprzedaży (POS/call center/Commerce handel elektroniczny)</li><li>Numer referencyjny PSP, jeśli sprawa dotyczyła konkretnej transakcji (Numer referencyjny PSP można znaleźć na pokwitowaniu, w strefie klienta Adyen lub w menu transakcji na terminalu POS).</li><li>Zrzut ekranu lub zdjęcie komunikatu o błędzie (jeśli ma zastosowanie)</li><li>Dzienniki podglądu zdarzeń (w formacie txt)</li><li>Opis prób rozwiązania problemu i jego rozwiązania</li></ul> |

## <a name="additional-resources"></a>Dodatkowe zasoby

[Akceptuj płatności za pomocą łącznika Adyen dla Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Łącznik płatności usługi Dynamics 365 dla Adyen](../dev-itpro/adyen-connector.md)

[Skonfiguruj łącznik płatności Adyen dla Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
