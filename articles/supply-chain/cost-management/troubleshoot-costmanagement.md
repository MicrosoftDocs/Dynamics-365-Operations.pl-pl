---
title: Rozwiązywanie problemów z zarządzaniem kosztami
description: W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z zarządzaniem kosztami.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b8c527e578fee6abfeeade99fba8070365c020bd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983857"
---
# <a name="troubleshoot-cost-management"></a>Rozwiązywanie problemów z zarządzaniem kosztami

W tym temacie opisano sposób rozwiązywania problemów, które mogą wystąpić podczas pracy z zarządzaniem kosztami.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Przerwy funkcjonalne między raportami wartości zapasów/wiekowania i ich wersji magazynowej

Funkcje [Magazyn raportów wiekowania zapasów](inventory-aging-report-storage.md) i [Raport magazynu wartości zapasów](inventory-value-report-storage.md) umożliwiają Supply Chain Management wyświetlanie dużych ilości transakcji magazynowych. W każdym przypadku wyniki raportów są zapisywane w celu przeglądania i eksportowania, w przeciwieństwie do wersji tych raportów bez magazynowania. Jednak niektóre funkcje, które istnieją w wersjach tych raportów bez magazynu, nie istnieją w wersjach magazynu. Poniższe podsekcje podsumowują różnice i udostępniają rozwiązania.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Raporty magazynowania nie zawierają sum częściowych, nawet jeśli są włączone w układzie raportu

Sumy częściowe mogą powodować problemy podczas eksportowania wyniku, zwłaszcza jeśli użytkownicy zmienią sekwencję rekordów.

Aby sprawdzić sumy częściowe, można wyeksportować wyniki do Microsoft Excel. Alternatywnie, jeśli chcesz sprawdzić sumy częściowe w ramach Supply Chain Management, użyj funkcji [Zarządzanie funkcjamit](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby włączyć funkcje *Kontrolka nowej siatki* i *(Wersja zapoznawcza) Grupowania w siatkach*, które zapewniają znacznie bardziej elastyczny sposób wyświetlania sum częściowych dla dowolnej grupy według kolumny. Aby uzyskać dodatkowe informacje, zobacz [Zdolności siatki](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Raport magazynowania wartości zapasów nie obsługuje informacji o koncie księgowym

Bilans próbny można uruchomić, aby uzyskać saldo konta zapasów i porównać je z raportem **Magazynu wartości zapasów**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Ostrzeżenia lub błędy są wyświetlane podczas zmiany stanu okresu księgi bez zamknięcia magazynu

Firma Microsoft wprowadziła następujące procesy weryfikacji, aby zapobiec problemom spowodowanym przez nieprawidłowy proces zakończenia okresu dotyczący kalkulacji kosztów. W przypadku napotkania dowolnego z poniższych komunikatów o błędach zapoznaj się z [4561987 KB](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3), aby uzyskać więcej informacji dotyczących sposobu rozwiązywania tych problemów.

- Zamierzasz wykonać ponowne obliczenie z datą %1 (10-02-2019). Ostatnie zarejestrowane ponowne obliczenie zostało wykonane w poprzednim okresie z datą %2 (20-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania. Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz zmienić stan okresu księgi %1 na %2. Nie zarejestrowano wykonania zamknięcia zapasów z datą %3, odpowiadającą zakończeniu okresu. Przed zmianą statusu należy wykonać zamknięcie zapasów na %3 odpowiadające końcowi okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji. Zgłoszone przez firmę %4. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Struktura konta %1 została zmieniona. Co najmniej jedno konto główne %2 już nie istnieje. Te konta główne są wymagane przez %3 z datą %4. Dodaj te konta główne do struktury konta %1, aby móc wznowić zadanie %3. Obecnie ta akcja ma wartość informacyjną, ale w przyszłości jej wykonanie będzie wymagane.

- Zamierzasz wykonać zamknięcie zapasów z datą %1 (31-01-2019). Nie zarejestrowano wykonania obliczania wyceny wstecznej z datą %2 (31-01-2019) pasującą do zakończenia okresu. Należy pamiętać o wykonaniu obliczania wyceny wstecznej z datą %3 (31-01-2019) pasującą do zakończenia okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do momentu wykonania tej operacji.

- Zamierzasz wykonać obliczenie wycent wstecznej z datą %1 (28-02-2019). Ostatnie zarejestrowane obliczenie wyceny wstecznej zostało wykonane w poprzednim okresie z datą %2 (31-01-2019). Nie zarejestrowano wykonania zamknięcia zapasów z datą %3 (31-01-2019) końca okresu dopasowania.
Należy pamiętać o wykonaniu zamknięcia zapasów w dacie %3 (31-01-2019), odpowiadającej zakończeniu okresu. Wycena zapasów, koszt własny sprzedaży i odchylenia mogą być niewłaściwe w księdze podrzędnej lub księdze głównej do wykonania zamknięcia zapasów.

## <a name="inventory-aging-report-discrepancies"></a>Rozbieżności w raportach wiekowania zapasów

**Raport wiekowania zapasów** zawiera różne wartości wyświetlane w różnych wymiarach przechowywania (np. oddział lub magazyn). Aby uzyskać więcej informacji o logice raportowania, zobacz [Przykłady i logika raportu wiekowania zapasów](inventory-aging-report.md).

## <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Konflikt aktualizacji występuje, gdy metodą inwentaryzacji zapasów jest Koszt standardowy lub Średnia ruchoma

Podczas równoległego księgowania dokumentów, takich jak arkusze magazynowe, faktury zamówień zakupu lub faktury zamówień sprzedaży, w celu uzyskania skalowalności i wydajności, może zostać wyświetlony komunikat o błędzie informujący o konflikcie aktualizacji i niektóre dokumenty mogą nie zostać zaksięgowane. Ten problem występuje, gdy metodą inwentaryzacji zapasów jest *Koszt standardowy* lub *Średnia ruchoma*. Obie te metody są metodami kosztów ciągłych. Innymi słowy, ostateczny koszt jest określony w momencie księgowania.

Jeśli jest stosowana metoda *Średnia ruchoma*, komunikat o błędzie przypomina ten przykład:

> Wartość zapasów xx,xx nie jest oczekiwana po obliczeniu proporcjonalnych wydatków

Jeśli jest stosowana metoda *Koszt standardowy*, komunikat o błędzie przypomina ten przykład:

> Koszt standardowy jest niezgodny z wartością zapasów finansowych po aktualizacji. Wartość = xx,xx, ilość = yy,yy, koszt standardowy = zz,zz

Do czasu wydania przez firmę Microsoft rozwiązania problemu należy rozważyć użycie następujących rozwiązań, aby wyeliminować lub zredukować te błędy:

- Zaksięguj ponownie dokumenty, których księgowanie nie powiodło się.
- Utwórz dokumenty z mniejszą liczbą wierszy.
- Unikaj wartości dziesiętnych kosztu standardowego. Spróbuj zdefiniować koszt standardowy, tak aby pole **Ilość dla ceny** było ustawione na *1*. Jeśli musisz określić wartość **ilości dla ceny** większą niż *1*, spróbuj zminimalizować liczbę miejsc dziesiętnych w standardowym koszcie jednostkowym. (Najlepiej, aby było mniej niż dwa miejsca dziesiętne) Na przykład należy unikać definiowania standardowych ustawień kosztu, takich jak **Cena** = *10* i **Ilość dla ceny** = *3*, ponieważ spowoduje to koszt standardowy jednostkowy 3,333333 (gdzie wartość dziesiętna jest powtarzana).
- W większości dokumentów należy unikać sytuacji, w których wiele wierszy zawiera taką samą kombinację wymiarów produktów i wymiarów magazynu finansowego.
- Zmniejsz stopień równoległości. (W takim przypadku system może przyspieszyć, ponieważ występuje mniej konfliktów i ponownych prób aktualizacji).
