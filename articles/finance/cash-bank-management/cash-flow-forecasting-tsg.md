---
title: Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych
description: W tym artykule znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych. Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.
author: angelad116
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 807a1da1906bdefec38954cea02ed29b0157d69e
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151410"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Rozwiązywanie problemów z ustawieniami prognozowania przepływów pieniężnych

[!include [banner](../includes/banner.md)]

W tym artykule znajdują się odpowiedzi na pytania, które mogą się pojawić podczas konfigurowania prognozowania przepływów pieniężnych. Zawiera odpowiedzi na często zadawane pytania (FAQ) dotyczące konfiguracji przepływu środków pieniężnych, aktualizacji przepływów pieniężnych i przepływów pieniężnych Power BI.

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

Upewnij się, że skonfigurowano miary „Miara przepływu pieniężnego V2” i „LedgerCovLiquidityMeasurement” z magazynu jednostek. Aby uzyskać więcej informacji na temat pracy z danymi Magazynu jednostek, zobacz [Integracja usługi Power BI z magazynem jednostek](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md). Sprawdź, czy wszystkie kroki wymagane do wyświetlenia zawartości Power BI zostały ukończone. Aby uzyskać więcej informacji, zobacz [Omówienie operacji gotówkowych - zawartość Power BI](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Czy jednostki magazynu jednostek zostały odświeżone?

Należy okresowo odświeżać jednostki, aby mieć pewność, że dane są aktualne i dokładne. Aby ręcznie odświeżyć określoną jednostkę, przejdź do **Administrowanie systemem \> Konfiguracja \> Magazyn jednostek**, wybierz tę jednostkę, a następnie wybierz opcję **Odśwież**. Dane mogą być również aktualizowane automatycznie. Na stronie **Magazyn jednostek** ustaw opcję **Automatyczne odświeżanie** na wartość **Tak**.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>Która metoda obliczania powinna być używana podczas obliczania prognoz przepływów pieniężnych?

Metoda obliczania prognozy przepływów pieniężnych ma dwie ważne opcje wyboru. Opcja **Nowa** spowoduje obliczanie prognoz przepływów pieniężnych dla nowych dokumentów i dokumentów, które uległy zmianie od czasu ostatniego zadania wsadowego. Ta opcja umożliwia szybsze uruchamianie, ponieważ przetwarza mniejszy podzestaw dokumentów. Opcja **Suma** spowoduje ponowne obliczanie prognoz przepływów pieniężnych dla każdego dokumentu w systemie. Ta opcja zajmuje więcej czasu, ponieważ wymaga więcej pracy do zakończenia.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>Jak zwiększyć wydajność cyklicznego zadania wsadowego prognoz przepływów pieniężnych?

Zaleca się uruchamianie prognozy przepływów pieniężnych każdego dnia poza godzinami szczytu, przy użyciu **Nowej** metody obliczania. Zalecane jest użycie tego podejścia przez sześć dni w tygodniu. Następnie uruchom prognozę przepływów pieniężnych raz w tygodniu przy użyciu metody obliczania **Suma** dla dnia z najmniejszą kwotą działania.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

