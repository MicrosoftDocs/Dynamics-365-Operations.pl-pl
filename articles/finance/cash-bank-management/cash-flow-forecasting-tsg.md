---
title: Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych
description: W tym temacie znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych. Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985294"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych

[!include [banner](../includes/banner.md)]

W tym temacie znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych. Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Dlaczego przepływ pieniężny jest pokazywany tylko dla jednej firmy?

Prognozowanie przepływów pieniężnych jest konfigurowane i obliczane dla firmy. Raporty usługi Power BI i możliwości prognozowania przepływów pieniężnych w narzędziu Finance Insights pokazują wyniki.

Prognozowanie przepływów pieniężnych musi być ustawione dla każdej firmy, dla której ma być ustawiona prognoza. Przejrzyj konfigurację prognozowania przepływów pieniężnych we wszystkich firmach. Alternatywnie przejrzyj konfigurację wszystkich firm do prognozowania przepływów pieniężnych i upewnij się, że są ustawione zgodnie z zamierzeniami.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Dlaczego usługa Power BI nie wyświetla wszystkich danych dotyczących przepływów pieniężnych?

Aby prognozy przepływów pieniężnych mogły pojawić się w widokach usługi Power BI, należy wykonać kilka kroków. Przejrzyj następującą listę kontrolną i upewnij się, że każdy krok został ukończony:

- Skonfiguruj przepływy pieniężne dla każdej firmy.
- W parametrach księgi głównej należy ustawić walutę systemową i systemowy typ kursu wymiany.
- Ustaw walutę rozliczeniową księgi i typ kursu wymiany.
- Wprowadź kursy wymiany między walutą transakcji a walutą rozliczeniową.
- Wprowadź kursy wymiany między walutą rozliczeniową a walutą systemu.
- Wprowadź kursy wymiany między walutą rozliczeniową a walutą każdego banku.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Dlaczego usługa Power BI przepływu środków pieniężnych działała w poprzednich wersjach, ale jest teraz pusta?

Upewnij się, że skonfigurowano miary „Miara przepływu pieniężnego V2” i „LedgerCovLiquidityMeasurement” z magazynu jednostek. Aby uzyskać więcej informacji dotyczących pracy z danymi w magazynie jednostek, zobacz [integrację Power BI z magazynem jednostek](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Sprawdź, czy zostały wykonane wszystkie kroki wymagane do wyświetlenia zawartości Power BI. Aby uzyskać więcej informacji, zobacz [Omówienie operacji gotówkowych - zawartość Power BI](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Czy jednostki magazynu jednostek zostały odświeżone?

Należy okresowo odświeżać jednostki, aby mieć pewność, że dane są aktualne i dokładne. Aby ręcznie odświeżyć określoną jednostkę, przejdź do **Administrowanie systemem \> Konfiguracja \> Magazyn jednostek**, wybierz tę jednostkę, a następnie wybierz opcję **Odśwież**. Dane mogą być również aktualizowane automatycznie. Na stronie **Magazyn jednostek** ustaw opcję **Automatyczne odświeżanie** na wartość **Tak**.
