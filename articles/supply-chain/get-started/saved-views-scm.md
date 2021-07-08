---
title: Standardowe zapisane widoki w aplikacji Supply Chain Management
description: W tym temacie opisano standardowe zapisane widoki, które są dostępne, oraz sposób ich włączania.
author: kamaybac
ms.date: 02/03/2021
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
ms.openlocfilehash: 1b1077fdb4707bf2c019e86cb073b30465817577
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270666"
---
# <a name="standard-saved-views-for-supply-chain-management"></a>Standardowe zapisane widoki w aplikacji Supply Chain Management

[!include [banner](../../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management zawiera kilka zapisanych widoków, które można włączyć i używać. Niektóre z tych standardowych zapisanych widoków są optymalizowane i nazwane dla określonej roli lub zadania (na przykład „Kontrola jakości” lub „Przyjęcie”). Inne są optymalizowane, tak aby uwzględniały tylko pola i ustawienia, które zgodnie ze statystykami Microsoft dotyczącymi użytkowania są najczęściej używane przez klientów. Te zapisane widoki są zazwyczaj nazywane widokami *uproszczonymi*. W tym temacie opisano standardowe zapisane widoki, które są dostępne, oraz sposób ich włączania i dostosowywania.

Aby uzyskać pełne szczegóły dotyczące pracy z zapisanymi widokami, w tym standardowymi zapisanymi widokami, po ich włączeniu zobacz temat [Zapisane widoki](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="customizing-the-standard-saved-views"></a>Dostosowywanie standardowych zapisanych widoków

Można dostosować standardowe zapisane widoki, podobnie jak własne zapisane widoki. Jednak podczas dostosowywania standardowego zapisanego widoku zdecydowanie zaleca się zapisanie niestandardowej wersji pod nową nazwą. W przeciwnym razie dostosowania mogą zostać zastąpione podczas aktualizowania aplikacji Supply Chain Management.

Aby uzyskać więcej informacji dotyczących dostosowywania zapisanych widoków i zmieniania ich nazw, zobacz temat [Zapisane widoki](../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json).

## <a name="available-saved-views-and-how-to-enable-them"></a>Dostępne zapisane widoki i sposób ich włączania

Aby korzystać z funkcji zapisanych widoków, niezależnie od tego, czy będziesz używać standardowych zapisanych widoków, należy włączyć funkcję *Zapisane widoki* w obszarze [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Pozostałe sekcje tego tematu zawierają tabele opisujące standardowe zapisane widoki, które są obecnie dostępne dla poszczególnych odpowiednich modułów. Każda tabela zawiera nazwę każdego zapisanego widoku, stronę, na której można go znaleźć, oraz opis tego widoku. W każdej tabeli jest również przedstawiana nazwa funkcji, która zawiera zapisany widok. Aby wyświetlić standardowy zapisany widok w systemie, należy włączyć określoną funkcję w [zarządzaniu funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="saved-views-for-the-inventory-management-module"></a>Zapisane widoki dla modułu Zarządzanie zapasami

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zarządzanie zapasami.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Lista dostępnych | Finanse | Ten uproszczony widok umożliwia skoncentrowanie się na informacjach finansowych podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami |
| Lista dostępnych | Kontrola jakości | Ten uproszczony widok umożliwia skoncentrowanie się na kontroli jakości podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami |
| Lista dostępnych | Przyjęcie | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach przyjęcia podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami |
| Lista dostępnych | Wysyłkowy | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach wysyłki podczas zarządzania dostępnymi zapasami. | Zapisane widoki dla zarządzania zapasami |
| Transakcje | Uproszczony | Ten uproszczony widok umożliwia przegląd stanu zapasów bez zakłóceń spowodowanych przez informacje finansowe i inne pola, które są używane rzadziej. | Zapisane widoki dla zarządzania zapasami |
| Zamówienia przeniesienia | Wysyłkowy | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach wysyłki podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami |
| Zamówienia przeniesienia | Przyjęcie | Ten uproszczony widok umożliwia skoncentrowanie się na operacjach przyjęcia podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami |
| Zamówienia przeniesienia | Kontrola jakości | Ten uproszczony widok umożliwia skoncentrowanie się na kontroli jakości podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami |
| Zamówienia przeniesienia | Finanse | Ten uproszczony widok umożliwia skoncentrowanie się na informacjach finansowych podczas zarządzania zamówieniami przeniesienia. | Zapisane widoki dla zarządzania zapasami |

## <a name="saved-views-for-the-master-planning-module"></a>Zapisane widoki dla modułu Planowanie główne

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Planowanie główne.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Zamówienia planowane: strona szczegółów zamówienia planowanego | Uproszczony | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do pracy ze szczegółami pojedynczego zamówienia planowanego. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla planowanych zamówień |
| Zamówienia planowane: strona listy zamówień planowanych | Uproszczony | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do pracy z listą zamówień planowanych. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla planowanych zamówień |

## <a name="saved-views-for-the-procurement-and-sourcing-module"></a>Zapisane widoki dla modułu Zaopatrzenie i sourcing

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zaopatrzenie i sourcing.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Szczegóły zamówienia zakupu | Tworzenie zamówień | Ten uproszczony widok został zoptymalizowany pod kątem tworzenia nowych zamówień zakupu. | Zapisane widoki dla zamówień zakupu |
| Szczegóły zamówienia zakupu | Zarządzanie zapasami | Ten uproszczony widok został zoptymalizowany pod kątem wykonywania działań związanych z zapasami, takich jak wykonywanie kolejnych czynności dla przyjętych zapasów, przyjmowanie zapasów, sprawdzanie wymagań netto i korygowanie ilości zamówień. | Zapisane widoki dla zamówień zakupu |
| Szczegóły zamówienia zakupu | Zarządzanie finansami | Ten uproszczony widok został zoptymalizowany pod kątem wykonywania działań związanych z finansami, takich jak fakturowanie i sprawdzanie cen, sum i opłat. | Zapisane widoki dla zamówień zakupu |
| Szczegóły zamówienia zakupu | Zatwierdzenie zamówienia | Ten uproszczony widok został zoptymalizowany pod kątem zatwierdzania zamówień zakupu. | Zapisane widoki dla zamówień zakupu |

## <a name="saved-views-for-the-production-control-module"></a>Zapisane widoki dla modułu Kontrola produkcji

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Kontrola produkcji.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Strona listy składowej (BOM) zlecenia produkcyjnego | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla kontroli produkcji |
| Strona szczegółów zlecenia produkcyjnego | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla kontroli produkcji |
| Strona listy pobrania zlecenia produkcyjnego | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla kontroli produkcji |
| Strona listy zleceń produkcyjnych | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisane widoki dla kontroli produkcji |

## <a name="saved-views-for-the-sales-and-marketing-module"></a>Zapisane widoki dla modułu Sprzedaż i marketing

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Sprzedaż i marketing.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Arkusz dokumentu dostawy | Przegląd arkusza | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przeglądania arkuszy dokumentów dostawy. | Zapisane widoki dotyczące sprzedaży i marketingu |
| Zamówienie sprzedaży | Tworzenie zamówień | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do tworzenia zamówień sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu |
| Zamówienie sprzedaży | Przegląd zamówienia | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przeglądania zamówień sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu |
| Oferta sprzedaży | Tworzenie oferty | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do tworzenia ofert sprzedaży. | Zapisane widoki dotyczące sprzedaży i marketingu |

## <a name="saved-views-for-the-warehouse-management-module"></a>Zapisane widoki dla modułu Zarządzanie magazynem

W poniższej tabeli opisano zapisane widoki dostępne dla modułu Zarządzanie magazynem.

| Strona | Nazwa widoku | Opis widoku | Nazwa funkcji |
|---|---|---|---|
| Wszystkie ładunki | Przetwarzanie przychodzące | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania ładunków przychodzących. | Zapisane widoki dla przetwarzania ładunku |
| Wszystkie ładunki | Przetwarzanie wychodzących | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania ładunków wychodzących. | Zapisane widoki dla przetwarzania ładunku |
| Wszystkie wysyłki | Przetwarzanie przychodzące | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania wysyłek przychodzących. | Zapisane widoki dla przetwarzania wysyłki |
| Wszystkie wysyłki | Przetwarzanie wychodzących | Ten uproszczony widok zawiera tylko pola, które są najczęściej używane do przetwarzania wysyłek wychodzących. | Zapisane widoki dla przetwarzania wysyłki |
| Wszystkie grupy czynności | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisany widok dla przetwarzania grupy czynności |
| Warsztat planowania wysyłki ładunku | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisany widok dla warsztatu planowania pracy |
| Szczegóły pracy | Uproszczony | Ten uproszczony widok zawiera tylko najczęściej używane pola. Dzięki temu zapewnia on szybszy przegląd i usprawnione procesy pracy. | Zapisany widok dla strony szczegółów pracy |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]