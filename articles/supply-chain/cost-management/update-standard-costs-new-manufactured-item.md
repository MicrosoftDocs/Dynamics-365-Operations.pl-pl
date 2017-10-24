---
title: "Aktualizacja kosztów standardowych nowo produkowanego towaru"
description: "Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych nowo produkowanego towaru."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9672b5063193ba62b731a9536fdca326cfaa7b6f
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Aktualizacja kosztów standardowych nowo produkowanego towaru

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych nowo produkowanego towaru. 

W poniższych wytycznych założono, że aktualizowanie kosztów standardowych obejmuje tworzenie dwóch wersji. W tej metodzie jedna wersja wyceny zawiera koszty standardowe zdefiniowane pierwotnie dla okresu zamrożenia, a druga wersja wyceny zawiera przyrostowe aktualizacje dotyczące nowo produkowanych towarów. Aktualizacje przyrostowe wprowadza się jako rekordy kosztów w drugiej wersji wyceny i na końcu są one włączane. Podejście z dwoma wersjami wymagana zdefiniowania drugiej wersji wyceny. Poniżej przedstawiono wytyczne dotyczące definiowania tej wersji wyceny:

-   Przypisz typ wyceny **Koszt standardowy**.
-   Przypisz sugestywny identyfikator wskazujący zawartość wersji wyceny, np. **2016-AKTUALIZACJE**.
-   W grupie pól **Zezwól na typy cen** upewnij się, że ustawienie **Koszt własny** ma wartość **Tak**.
-   Pozwól na wprowadzanie rekordów kosztów we wszystkich oddziałach (tzn. pozostaw puste pole **Oddział**). Jeśli określisz oddział, rekordy kosztów można wprowadzić tylko w tym oddziale.
-   Użyj zasady alternatywnego źródła **Aktywne**.

Aby dodawać nowe towary produkcyjne przez cały okres zamrożenia, wykonaj poniższe czynności.

1.  Na stronie **Konfiguracja wersji wyceny** włącz możliwość wprowadzania rekordów kosztów do drugiej wersji wyceny, tzn. tej, która zawiera aktualizacje przyrostowe. Zablokuj możliwość aktywacji kosztów oczekujących, tak aby aktywacja była dozwolona dopiero po całkowitym i dokładnym zdefiniowaniu tych kosztów. Wskaż pustą datę początkową jako zasadę w wersji wyceny, a następnie wprowadź datę początkową przy wprowadzaniu każdego rekordu kosztów. Data początkowa powinna reprezentować datę przed zakupem lub wyprodukowaniem nowych towarów.
2.  Na stronie **Cena pozycji** wprowadź rekordy kosztów nowo kupowanych towarów. Dla każdego rekordu kosztów wprowadź wersję wyceny zawierającą aktualizacje przyrostowe oraz użyj daty początkowej wcześniejszej niż przewidywana data produkcji nowo wytwarzanych towarów.
3.  Oblicz koszt nowo produkowanych towarów, korzystając ze strony **Obliczanie**. Otwórz stronę **Obliczanie** ze strony **Obsługa wersji wyceny**, a następnie wybierz wersję wyceny zawierającą aktualizacje przyrostowe. Użyj kryteriów wyboru, aby określić nowo produkowany towar oraz dowolny z jego produkowanych składników. W wielopoziomowej strukturze produktów może być również konieczne określenie dowolnego towaru nadrzędnego, który zawiera nowo produkowany towar jako składnik. Wprowadź datę początkową dla obliczania listy składowej (BOM) odpowiadającą dacie rozpoczęcia produkcji nowo wytwarzanych towarów. Data początkowa powinna się mieścić w zakresie dat obowiązywania wersji BOM towaru i wersji marszruty. **Uwaga:** Brak rekordu kosztów może oznaczać, że jest to nowo produkowany towar. Obliczenia BOM można ograniczyć do towarów z brakującymi kosztami.
4.  Sprawdź kompletność i dokładność obliczonych kosztów nowo produkowanych towarów. Na stronie **Zakończono** możesz przejrzeć obliczone koszty dla poszczególnych rekordów kosztów towarów oraz wszelkie komunikaty ostrzegawcze zawarte w dzienniku informacyjnym. Alternatywnie obliczone koszty można przejrzeć na stronie **Obliczanie**.
5.  Za pomocą strony **Konfiguracja wersji wyceny** zmień flagę blokowania, aby umożliwić aktywowanie rekordów kosztów oczekujących w drugiej wersji wyceny.
6.  Na stronie **Aktywuj ceny** (którą można otworzyć ze strony **Obsługa wersji wyceny**) włącz wszystkie rekordy kosztów oczekujących w drugiej wersji wyceny. Można również włączyć rekordy kosztów oczekujących dla poszczególnych towarów, klikając przycisk **Aktywuj** umieszczony na stronie **Cena pozycji**.
7.  Za pomocą strony **Konfiguracja wersji wyceny** zmień flagi blokowania w drugiej wersji wyceny, tak aby uniemożliwić dalsze modyfikowanie danych. Zasady blokowania zapobiegają wprowadzaniu nowych kosztów oczekujących i aktywowaniu kosztów oczekujących.





