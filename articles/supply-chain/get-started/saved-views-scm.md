---
title: Standardowe zapisane widoki w aplikacji Supply Chain Management
description: W tym artykule opisano standardowe zapisane widoki, które są dostępne, oraz sposób ich włączania.
author: kamaybac
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f94fffb9aa2c208b8c2c0005a2892853eda66a01
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334844"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Standardowe zapisane widoki w aplikacji Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management zawiera kilka zapisanych widoków, które można włączyć i używać. Niektóre z tych standardowych zapisanych widoków są optymalizowane i nazwane dla określonej roli lub zadania (na przykład „Kontrola jakości” lub „Przyjęcie”). Inne są optymalizowane, tak aby uwzględniały tylko pola i ustawienia, które zgodnie ze statystykami Microsoft dotyczącymi użytkowania są najczęściej używane przez klientów. Te zapisane widoki są zazwyczaj nazywane widokami *uproszczonymi*. W tym artykule opisano standardowe zapisane widoki, które są dostępne, oraz sposób ich włączania i dostosowywania.

Aby uzyskać pełne szczegóły dotyczące pracy z zapisanymi widokami, w tym standardowymi zapisanymi widokami, po ich włączeniu zobacz temat [Zapisane widoki](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Dostosowywanie standardowych zapisanych widoków

Można dostosować standardowe zapisane widoki, podobnie jak własne zapisane widoki. Jednak podczas dostosowywania standardowego zapisanego widoku zdecydowanie zaleca się zapisanie niestandardowej wersji pod nową nazwą. W przeciwnym razie dostosowania mogą zostać zastąpione podczas aktualizowania aplikacji Supply Chain Management.

Aby uzyskać więcej informacji dotyczących dostosowywania zapisanych widoków i zmieniania ich nazw, zobacz temat [Zapisane widoki](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Dostępne zapisane widoki i sposób ich włączania

Aby korzystać z funkcji zapisanych widoków, niezależnie od tego, czy będziesz używać standardowych zapisanych widoków, należy włączyć funkcję *Zapisane widoki* w obszarze [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (od wersji 10.0.21 ta funkcja jest domyślnie włączona).

Pozostałe sekcje tego artykułu zawierają tabele opisujące standardowe zapisane widoki, które są obecnie dostępne dla poszczególnych odpowiednich modułów. Każda tabela zawiera nazwę każdego zapisanego widoku, stronę, na której można go znaleźć, oraz opis tego widoku. W każdej tabeli jest również przedstawiana nazwa funkcji, która zawiera zapisany widok. Aby wyświetlić standardowy zapisany widok w systemie, należy włączyć określoną funkcję w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). W wersji 10.0.25 wszystkie wyświetlane widoki są domyślnie włączone.

## <a name="saved-views-for-the-inventory-management-module"></a>Zapisane widoki dla modułu Zarządzanie zapasami

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zarządzanie zapasami.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Lista dostępnych | Finanse | Ten uproszczony widok umożliwia skoncentrowanie się na informacjach finansowych podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Lista dostępnych | Kontrola jakości | Ten uproszczony widok umożliwia skoncentrowanie się na kontroli jakości podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Lista dostępnych | Odbieranie | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach przyjęcia podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Lista dostępnych | Wysyłkowy | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach wysyłki podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Transakcje | Uproszczone | Ten uproszczony widok umożliwia przegląd stanu zapasów bez zakłóceń spowodowanych przez informacje finansowe i inne pola, które są używane rzadziej. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Zamówienia przeniesienia | Wysyłkowy | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach wysyłki podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Zamówienia przeniesienia | Odbieranie | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach przyjęcia podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Zamówienia przeniesienia | Kontrola jakości | Ten uproszczony widok umożliwia skoncentrowanie się na kontroli jakości podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Zamówienia przeniesienia | Finanse | Ten uproszczony widok umożliwia skoncentrowanie się na informacjach finansowych podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-master-planning-module"></a>Zapisane widoki dla modułu Planowanie główne

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Planowanie główne.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Zamówienia planowane: strona szczegółów zamówienia planowanego | Uproszczony | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do pracy ze szczegółami pojedynczego zamówienia planowanego. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla planowanych zamówień<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Zamówienia planowane: strona listy zamówień planowanych | Uproszczone | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do pracy z listą zamówień planowanych. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla planowanych zamówień<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Zapisane widoki dla modułu Zaopatrzenie i sourcing

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zaopatrzenie i sourcing.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Szczegóły zamówienia zakupu | Tworzenie zamówień | Ten uproszczony widok został zoptymalizowany pod kątem tworzenia nowych zamówień zakupu. | Zapisane widoki dla zamówień zakupu<br><br>Domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Szczegóły zamówienia zakupu | Zarządzanie zapasami | Ten uproszczony widok został zoptymalizowany pod kątem wykonywania działań związanych z zapasami, takich jak wykonywanie kolejnych czynności dla przyjętych zapasów, przyjmowanie zapasów, sprawdzanie wymagań netto i korygowanie ilości zamówień. | Zapisane widoki dla zamówień zakupu<br><br>Domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Szczegóły zamówienia zakupu | Zarządzanie finansami | Ten uproszczony widok został zoptymalizowany pod kątem wykonywania działań związanych z finansami, takich jak fakturowanie i sprawdzanie cen, sum i opłat. | Zapisane widoki dla zamówień zakupu<br><br>Domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Szczegóły zamówienia zakupu | Zatwierdzanie zamówienia | Ten uproszczony widok został zoptymalizowany pod kątem zatwierdzania zamówień zakupu. | Zapisane widoki dla zamówień zakupu<br><br>Domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-product-information-management-module"></a>Zapisane widoki dla modułu Zarządzanie informacjami o produktach

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zarządzanie informacjami o produktach.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Lista zwolnionych produktów | Tworzenie produktu | Uproszczony widok strony, który zawiera tylko pola używane najczęściej podczas tworzenia produktów. | Zapisane widoki zwolnionych produktów<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Szczegóły zwolnionego produktu | Tworzenie produktu | Uproszczony widok strony, który zawiera tylko pola używane najczęściej podczas tworzenia produktów. | Zapisane widoki zwolnionych produktów<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Szczegóły zwolnionego produktu | Zarządzanie informacjami logistycznymi | Uproszczony widok strony, który zawiera tylko pola używane najczęściej podczas zarządzania informacjami logistycznymi dla produktów. | Zapisane widoki zwolnionych produktów<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Szczegóły zwolnionego produktu | Zarządzanie informacjami związanymi z zakupem | Uproszczony widok strony, który zawiera tylko pola używane najczęściej podczas zarządzania informacjami związanymi z zakupem dla produktów. | Zapisane widoki zwolnionych produktów<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Szczegóły zwolnionego produktu | Zarządzanie informacjami związanymi ze sprzedażą | Uproszczony widok strony, który zawiera tylko pola używane najczęściej podczas zarządzania informacjami związanymi ze sprzedażą dla produktów. | Zapisane widoki zwolnionych produktów<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-production-control-module"></a>Zapisane widoki dla modułu Kontrola produkcji

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Kontrola produkcji.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Strona listy składowej (BOM) zlecenia produkcyjnego | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki kontroli produkcji<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Strona szczegółów zlecenia produkcyjnego | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki kontroli produkcji<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Strona listy pobrania zlecenia produkcyjnego | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki kontroli produkcji<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |
| Strona listy zleceń produkcyjnych | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki kontroli produkcji<br><br>(domyślnie w wersji 10.0.21. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Zapisane widoki dla modułu Sprzedaż i marketing

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Sprzedaż i marketing.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Arkusz dokumentu dostawy | Przegląd arkusza | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przeglądania arkuszy dokumentów dostawy. | Zapisane widoki dotyczące sprzedaży i marketingu<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Zamówienie sprzedaży | Tworzenie zamówienia | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do tworzenia zamówień sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Zamówienie sprzedaży | Przegląd zamówienia | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przeglądania zamówień sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Oferta sprzedaży | Tworzenie oferty | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do tworzenia ofert sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |

## <a name="saved-views-for-the-warehouse-management-module"></a>Zapisane widoki dla modułu Zarządzanie magazynem

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zarządzanie magazynem.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Wszystkie ładunki | Przetwarzanie przychodzące | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania ładunków przychodzących. | Zapisane widoki dla przetwarzania ładunku<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Wszystkie ładunki | Przetwarzanie wychodzących | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania ładunków wychodzących. | Zapisane widoki dla przetwarzania ładunku<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Wszystkie wysyłki | Przetwarzanie przychodzących | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania wysyłek przychodzących. | Zapisane widoki dla przetwarzania wysyłki<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Wszystkie wysyłki | Przetwarzanie wychodzących | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania wysyłek wychodzących. | Zapisane widoki dla przetwarzania wysyłki<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Wszystkie grupy czynności | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisany widok dla przetwarzania grupy czynności<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Warsztat planowania wysyłki ładunku | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla warsztatu planowania wysyłki ładunku<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |
| Szczegóły pracy | Uproszczone | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisany widok dla strony szczegółów pracy<br><br>(domyślnie w wersji 10.0.25. obowiązkowo od wersji 10.0.29). |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]