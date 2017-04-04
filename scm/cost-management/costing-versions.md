---
title: Wersje wyceny
description: "Ten artykuł zawiera informacje o wersjach wyceny, zarządzaniu nimi oraz o typach danych, które można w nich uwzględnić. Głównym celem wersji wyceny jest objęcie rekordów kosztów dotyczących towarów, kategorii kosztów oraz wzorów obliczania kosztów pośrednich."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: ec2f6ad748d4b89a72347314a9cf9dcacd8196a8
ms.lasthandoff: 03/29/2017


---

# <a name="costing-versions"></a>Wersje wyceny

Ten artykuł zawiera informacje o wersjach wyceny, zarządzaniu nimi oraz o typach danych, które można w nich uwzględnić. Głównym celem wersji wyceny jest objęcie rekordów kosztów dotyczących towarów, kategorii kosztów oraz wzorów obliczania kosztów pośrednich.

Wersja wyceny może spełniać jeden lub kilka celów w oparciu o dane, które są zawarte w wersji wyceny. Głównym celem wersji wyceny jest objęcie rekordów kosztów dotyczących towarów, kategorii kosztów oraz wzorów obliczania kosztów pośrednich. Wersja wyceny może zawierać zestaw rekordów kosztów standardowych lub zestaw rekordów kosztów planowanych, które opierają się na typie wyceny, która jest przypisana do wersji wyceny.

## <a name="costing-versions-for-standard-or-planned-costs"></a>Tworzenie wersji ceny opartej na kosztach standardowych lub planowanych.
### <a name="standard-costs"></a>Koszty standardowe

Wersja wyceny może obsługiwać model magazynu kosztów standardowych dla towarów, gdzie wersja wyceny zawiera zestaw rekordów kosztów standardowych o towarach i procesach produkcyjnych. Dane kosztów dotyczące procesów produkcyjnych są wyrażane w formie kategorii kosztów dla operacji marszruty oraz wzorów obliczeniowych dla narzutów produkcji.

### <a name="planned-costs"></a>Koszty planowane

Wersja wyceny może zawierać zestaw rekordów kosztów planowanych dotyczących towarów i procesów produkcyjnych. Wersja wyceny z kosztami planowanymi często jest używana do wspomagania symulacji obliczania kosztów, takich jak symulacja wpływu zmiany kosztów na zakup materiałów lub procesów produkcyjnych na obliczone koszty produkowanych towarów. Rekordy kosztów towarów dla kosztów planowanych mogą być również używane do wspomagania modelu zapasów opartego na kosztach rzeczywistych poprzez dostarczenie początkowych wartości kosztów towarów. Wartości te obejmują obliczanie kosztów planowanych dla produkowanych towarów.

## <a name="entering-costs"></a>Wprowadzanie kosztów
Obsługa danych rekordów kosztów w ramach wersji wyceny obejmuje wprowadzanie kosztów dla zakupionych towarów oraz dla towarów, które są przesyłane pomiędzy oddziałami. Dodatkowa obsługa danych dla producentów obejmuje wprowadzanie kosztów dla kategorii kosztów (powiązanych z operacjami marszruty), wprowadzanie wzorów obliczania dla kosztów pośrednich obrazujących narzuty produkcyjne oraz obliczanie kosztów dla wyprodukowanych towarów. 

Dane kosztów towaru w ramach wersji wyceny będą składać się z jednego lub kilku rekordów kosztu dla każdego towaru. Rekord kosztu towaru początkowo jest wprowadzany ze stanem **Oczekujący** oraz zamierzoną datą wprowadzenia. Aktywacja rekordu kosztu towaru aktualizuje stan (do wartości **Aktywny**)i datę wprowadzenia (do daty aktywacji). Różne rekordy kosztu towaru mogą odzwierciedlać różne oddziały, daty efektywne lub stany. W przypadku obliczania kosztów dla wyprodukowanych towarów dla daty przyszłej, obliczenie listy składowej (BOM) będzie jedynie obejmować rekordy kosztu z odpowiednią datą wprowadzenia, niezależnie od tego, czy stan ma wartość **Oczekujący** czy **Aktywny**. Bieżący aktywny rekord kosztu towaru będzie użyty do oszacowania kosztów zlecenia produkcyjnego i transakcji magazynowych w ramach modelu magazynu wyceny standardowej. Obsługa rekordów kosztów dla kategorii kosztów oraz wzorów obliczania kosztów pośrednich jest podobna do obsługi rekordów kosztu towaru. 

Dwie polityki blokowania dla wersji wyceny określają, czy koszty oczekujące mogą być obsługiwane oraz czy koszty oczekujące mogą być aktywowane. Użyj polityki blokowania do umożliwienia obsługi danych, a następnie do uniemożliwienia obsługi danych dla rekordów kosztu w ramach wersji wyceny. 

Wersja wyceny może również zawierać dane dotyczące cen sprzedaży towaru lub cen zakupu w celu obliczenia BOM.

## <a name="item-sales-prices-for-bom-calculations"></a>Ceny sprzedaży towaru dla obliczeń BOM
Głównym powodem, dla którego uwzględnia się dane o cenach sprzedaży, jest możliwość zachowania obliczonej ceny sprzedaży wyprodukowanego towaru. Obliczona cena sprzedaży może być analizowana w celu określenia sposobu wpływania składników, operacji marszruty i narzutów na koszt i cenę sprzedaży. 

Drugim powodem, dla którego uwzględnia się dane o cenach sprzedaży, jest definiowanie rekordów ceny sprzedaży dla towarów składowych. Rekordy te mogą być następnie używane do obliczania ceny sprzedaży produkowanych towarów. Najpierw trzeba określić model ceny sprzedaży znajdujący się w grupie obliczeń BOM i przypisać tę grupę do zakupionych towarów. Następnie, podczas wykonywania obliczeń BOM z użyciem kosztów planowanych, należy wybrać model kosztu własnego grupy obliczeń BOM. 

W przeciwnym razie rekordy ceny sprzedaży towarów są używane tylko w celach informacyjnych, bez względu na to, czy są wprowadzane ręcznie, czy obliczane. Aktywując rekord ceny sprzedaży towaru, można zaktualizować podstawą cenę sprzedaży towaru. Jednak podstawa cena sprzedaży nie jest właściwa dla oddziału i może zastąpić ją ręcznie. Podstawowa cena sprzedaży służy jako domyślna cena sprzedaży w zamówieniach sprzedaży i ofertach sprzedaży.

## <a name="item-purchase-prices-for-bom-calculations"></a>Ceny zakupu towaru dla obliczeń BOM
Głównym powodem dopuszczenia występowania cen zakupu w tym miejscu jest możliwość definiowania rekordów cen zakupu dla towarów składowych, których można później użyć do obliczania kosztów wyprodukowanych towarów. Rekordy ceny zakupu towaru muszą być wprowadzane ręcznie. 

Aby włączyć dane cen zakupu, należy najpierw zdefiniować grupę obliczania BOM zawierającą model kosztu własnego dla ceny zakupu towaru i przypisać grupę obliczeń BOM do zakupionych towarów. Następnie należy użyć modelu kosztu własnego dla grupy obliczeń BOM podczas obliczania BOM z użyciem kosztów planowanych do obliczenia ceny sprzedaży produkowanych towarów. 

Rekordy ceny zakupu dla towarów są również używane w celach informacyjnych. Zmieniając stan rekordu ceny zakupu towaru z **Oczekujący** na **Aktywny**, można zaktualizować podstawową cenę zakupu towaru. Jednak podstawa cena zakupu nie jest właściwa dla oddziału i może zastąpić ją ręcznie. Podstawowa cena zakupu służy jako domyślna cena zakupu w zamówieniach zakupu.


