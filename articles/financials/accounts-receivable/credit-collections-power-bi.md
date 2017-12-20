---
title: "Pakiet zawartości usługi Power BI Zarządzanie kredytami i windykacją"
description: "W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Power BI Zarządzanie kredytami i windykacją. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations. Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 536ebae3ec44954aba314a966c9b0d2dabef45d1
ms.contentlocale: pl-pl
ms.lasthandoff: 12/01/2017

---

# <a name="credit-and-collections-management-power-bi-content"></a>Pakiet zawartości usługi Power BI Zarządzanie kredytami i windykacją

W tym temacie opisano, co się znajduje w pakiecie zawartości usługi Microsoft Power BI **Zarządzanie kredytami i windykacją**. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu.

## <a name="overview"></a>Przegląd

Pakiet zawartości usługi Power BI zatytułowany **Zarządzanie kredytami i windykacją** jest przeznaczony dla kierowników ds. kredytów i windykacji oraz dla pracowników ds. windykacji. Zawiera najważniejsze mierniki kredytu i windykacji, takie jak wskaźnik rotacji należności w dniach, saldo zaległości, kwota udzielonych kredytów oraz odbiorcy z przekroczonym limitem kredytu. Wykorzystuje dane transakcyjne i przedstawia zagregowane widoki kredytów i windykacji dla wszystkich firm. Prezentuje także podział na firmy, grupy odbiorców i odbiorców.

Ten pakiet zawartości usługi Power BI zawiera 10 stron raportów:

- Dwie strony informacji ogólnych (jedna dla kredytów i jedna dla windykacji)
- Osiem stron szczegółów, które zawierają szczegółowe informacje o miernikach kredytów i windykacji według różnych wymiarów

Wszystkie kwoty są wyświetlane w walucie systemowej. Można ustawiać walutę systemową na stronie **Parametry systemowe**.

Domyślnie są wyświetlane dane kredytów i windykacji dla bieżącej firmy. Aby wyświetlić dane dla wszystkich firm, należy przypisać obowiązek **CustCollectionsBICrossCompany** do roli.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI
Zawartość usługi Power BI **Zarządzanie kredytami i windykację** jest wyświetlana w obszarze roboczym **Kredyty i windykacja odbiorcy**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Raporty umieszczone w pakiecie zawartości usługi Power BI

Pakiet zawartości usługi Power BI **CustCollectionsBICrossCompany** obejmuje raport zawierający zbiór mierników. Te wskaźniki są wizualizowane jako wykresy, kafelki i tabele. Poniższa tabela zawiera omówienie wizualizacji dostępnych w pakiecie zawartości usługi Power BI **CustCollectionsBICrossCompany**.

| Strona raportu                 | Wizualizacja |
|-----------------------------|---------------|
| Przegląd windykacji        | <ul><li>Odbiorcy — zaległe</li><li>Odbiorcy przekraczający limit kredytu</li><li>DSO 30 dni</li><li>Otwarte sprawy</li><li>Średnia liczba dni do zamknięcia sprawy</li><li>Otwarte działania</li><li>Średnia liczba dni do zamknięcia działań</li><li>Otwarte noty odsetkowe</li><li>Otwarte ponaglenia</li><li>Wstrzymanie odbiorcy</li><li>Wstrzymanie sprzedaży</li><li>Wiekowane salda</li><li>Kwoty stanu windykacji</li><li>Kwoty kodu windykacji</li><li>Przyczyna odpisu</li><li>Saldo należne według regionów</li><li>Oczekiwane płatności</li></ul> |
| Przegląd kredytów             | <ul><li>Odbiorcy — zaległe</li><li>Limit kredytu a saldo należne</li><li>Tabela odbiorców przekraczających limit kredytu</li><li>Odbiorcy przekraczający limit kredytu na firmę</li><li>Kredyt wykorzystany a łączny limit kredytu</li><li>Limit kredytu a kredyt wykorzystany według regionów</li><li>Odbiorcy na ocenę kredytu</li></ul> |
| Limit kredytu                | <ul><li>Limit kredytu</li><li>Szczegóły limitu kredytu</li><li>Limit kredytu na odbiorcę</li><li>Limit kredytu na grupy odbiorców</li><li>Limit kredytu na ocenę kredytu na firmę</li><li>Limit kredytu a kredyt wykorzystany według regionów</li></ul> |
| Odbiorcy przekraczający limit kredytu | <ul><li>Odbiorcy przekraczający limit kredytu</li><li>Szczegóły odbiorców przekraczających limit kredytu</li><li>Odbiorcy przekraczający limit kredytu na firmę</li><li>Odbiorca przekraczający limit kredytu na grupę odbiorców</li><li>Odbiorcy przekraczający limit kredytu na region</li></ul> |
| Odbiorcy — zaległe          | <ul><li>Odbiorcy — zaległe</li><li>Szczegóły zaległości odbiorców</li><li>Zaległości odbiorców według firmy</li><li>Zaległości odbiorców według grupy odbiorców</li><li>Zaległości odbiorców według regionów</li></ul> |
| Wiekowane salda               | <ul><li>Wiekowane salda</li><li>Szczegóły wiekowanych sald</li><li>Wiekowane salda według firmy</li><li>Wiekowane salda według grup odbiorców</li></ul> |
| Oczekiwane płatności           | <ul><li>Oczekiwane płatności</li><li>Szczegóły oczekiwanych płatności</li><li>Oczekiwane płatności według firmy</li><li>Oczekiwane płatności według grupy odbiorców</li><li>Oczekiwane płatności według regionów</li></ul> |
| Odpisy                  | <ul><li>Odpisy według regionów</li><li>Szczegóły odpisów</li><li>Odpisy według kont głównych</li><li>Odpisy według firm</li><li>Odpisy według grup odbiorców</li><li>Odpisy według regionów</li></ul> |
| Stan windykacji          | <ul><li>Sporne</li><li>Złamane przyrzeczenie zapłaty</li><li>Przyrzeczenie zapłaty</li><li>Szczegóły stanu windykacji</li><li>Kwoty stanu windykacji</li><li>Otwarte sprawy</li><li>Otwarte działania</li></ul> |
| Ponaglenia         | <ul><li>Kwoty kodu ponaglenia</li><li>Szczegóły kwoty kodu ponaglenia</li><li>Kwoty ponagleń według firmy</li><li>Kwoty ponagleń według grupy odbiorców</li><li>Kwoty ponagleń według regionów</li></ul> |

Wykresy i kafelki we wszystkich tych raportach można filtrować i przypinać do pulpitu nawigacyjnego. Aby uzyskać więcej informacji na temat filtrowania i przypinania w narzędziu Power BI, zobacz [Tworzenie i konfigurowanie pulpitu nawigacyjnego](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Można także użyć funkcji eksportu danych źródłowych do wyeksportowania danych podsumowanych w wizualizacji.

## <a name="extending-the-power-bi-content"></a>Rozszerzanie funkcjonalności pakietu zawartości usługi Power BI
Za pomocą pakietów zawartości dostępnych w usłudze Microsoft Dynamics Lifecycle Services (LCS) można dostarczać zaawansowane funkcje analityczne osobom, które się nie logują w programie Finance and Operations. Te pakiety zawartości można modyfikować, tak aby zawierały inne raporty lub wizualizacje, a następnie publikować je w swojej dzierżawie usługi Power BI.com na potrzeby wykonywania analiz.

Pakiet zawartości usługi Power BI **Zarządzanie kredytami i windykacją** znajduje się w bibliotece zasobów wspólnych w usłudze LCS. Aby dowiedzieć się więcej o pobieraniu pakietu zawartości i jego implementowaniu w swojej organizacji, zobacz [Pakiety zawartości dla usługi Power BI w usłudze LCS od Microsoft i partnerów](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Aby obejrzeć demonstrację przedstawiającą sposób implementowania pakietu zawartości usługi Power BI, zobacz materiał z serii Office Mix [Pakiety zawartości dla usługi Power BI w usłudze Dynamics Lifecycle Services od Microsoft i partnerów](https://mix.office.com/watch/9puyb1b2xs1w).

Uważaj, aby pobrać pakiet zawartości **Zarządzanie kredytami i windykacją** usługi Power BI odpowiedni do używanej wersji programu Finance and Operations.

## <a name="understanding-the-data-model-and-entities"></a>Opis modelu danych i jednostek

Następujące dane są używane do wypełniania raportów w pakiecie zawartości usługi Power BI **Zarządzanie kredytami i windykacją**. Te dane są reprezentowane jako zagregowane miary umieszczone w magazynie jednostek. Magazyn jednostek to baza danych programu Microsoft SQL Server zoptymalizowana pod kątem analiz. Aby uzyskać więcej informacji, zobacz [Omówienie integracji usługi Power BI z magazynem jednostek](../../dev-itpro/analytics/power-bi-integration-entity-store.md).

| Jednostka                                      | Najważniejsze zagregowane miary           | Źródło danych                                 | Pole                                                      | opis |
|---------------------------------------------|--------------------------------------|---------------------------------------------|------------------------------------------------------------|-------------|
| CustCollectionsBIActivitiesAverageCloseTime | NumOfActivities, AveragecClosedTime  | smmActivities                               | AverageOfChildren(AverageClosedTime) Count(ActivityNumber) | Liczba zamkniętych działań i średni czas potrzebny do zamknięcia tych działań. |
| CustCollectionsBIActivitiesOpen             | ActivityNumber                       | smmActivities                               | Count(ActivityNumber)                                      | Liczba otwartych działań. |
| CustCollectionsBIAgedBalances               | AgedBalances                         | CustCollectionsBIAgedBalancesView           | Sum(SystemCurrencyBalance)                                 | Suma wiekowanych sald. |
| CustCollectionsBIBalancesDue                | SystemCurrencyAmount                 | CustCollectionsBIBalanceDueView             | Sum(SystemCurrencyAmount)                                  | Kwoty, które są zaległe. |
| CustCollectionsBICaseAverageCloseTIme       | NumOfCases, CaseAverageClosedTime    | CustCollectionsCaseDetail                   | AverageOfChildren(CaseAverageClosedTime) Count(NumOfCases) | Liczba zamkniętych spraw i średni czas potrzebny do zamknięcia tych spraw. |
| CustCollectionsBICasesOpen                  | CaseId                               | CustCollectionsCaseDetail                   | Count(CaseId)                                              | Liczba otwartych spraw. |
| CustCollectionsBICollectionLetter           | CollectionLetterNum                  | CustCollectionLetterJour                    | Count(CollectionLetterNum)                                 | Liczba otwartych ponagleń. |
| CustCollectionsBICollectionLetterAmount     | CollectionLetterAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldo zaksięgowanych ponagleń. |
| CustCollectionsBICollectionStatus           | CollectionStatusAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldo transakcji ze stanem windykacji. |
| CustCollectionsBICredit                     | CreditExposed, AmountOverCreditLimit | CustCollectionsBICreditView                 | Sum(CreditExposed), Sum(AmountOverCreditLimit)             | Suma udzielonych kredytów oraz kwoty, o jakie odbiorcy przekraczają swoje limity kredytowe. |
| CustCollectionsBICustOnHold                 | Zablokowana                              | CustCollectionsBICustTable                  | Count(Blocked)                                             | Liczba odbiorców, którzy są wstrzymani. |
| CustCollectionsBIDSO                        | DSO30                                | CustCollectionsBIDSOView                    | AverageOfChildren(DSO30)                                   | Wskaźnik rotacji należności wynoszący co najmniej 30 dni. |
| CustCollectionsBIExpectedPayment            | ExpectedPayment                      | CustCollectionsBIExpectedPaymentView        | Sum(SystemCurrencyAmounts)                                 | Suma oczekiwanych płatności w ciągu najbliższego roku. |
| CustCollectionsBIInterestNote               | InterestNote                         | CustInterestJour                            | Count(InterestNote)                                        | Liczba not odsetkowych, które zostały utworzone. |
| CustCollectionsBISalesOnHold                | SalesId                              | SalesTable                                  | Count(SalesId)                                             | Łączna liczba zamówień sprzedaży, które są wstrzymane. |
| CustCollectionsBIWriteOff                   | WriteOffAmount                       | CustCollectionsBIWriteOffView               | Sum(SystemCurrencyAmount)                                  | Suma transakcji, które zostały odpisane. |

