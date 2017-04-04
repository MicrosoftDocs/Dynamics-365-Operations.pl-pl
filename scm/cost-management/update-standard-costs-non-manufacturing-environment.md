---
title: "Aktualizacja kosztów standardowych w środowisku nieprodukcyjnym"
description: "Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku nieprodukcyjnym."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: be3e5417341094caf0565c1c5ee4f9cbc40f8e76
ms.lasthandoff: 03/31/2017


---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Aktualizacja kosztów standardowych w środowisku nieprodukcyjnym

Ten artykuł zawiera wskazówki dotyczące aktualizowania kosztów standardowych w środowisku nieprodukcyjnym.

W poniższych wytycznych założono, że aktualizowanie kosztu standardowego obejmuje tworzenie dwóch wersji. W tej metodzie jedna wersja wyceny zawiera koszty standardowe zdefiniowane pierwotnie dla okresu zamrożenia, a druga wersja wyceny zawiera przyrostowe aktualizacje. Każdą aktualizację wprowadza się jako rekord kosztu umieszczony w drugiej wersji wyceny i na końcu włączany. W alternatywnym podejściu z jedną wersją jest używany zbiór standardowych kosztów, które pierwotnie zdefiniowano. Podejście z dwoma wersjami wymagana zdefiniowania drugiej wersji wyceny. Poniżej przedstawiono wytyczne dotyczące definiowania tej wersji wyceny:

-   Przypisz typ wyceny **Koszty standardowe**.
-   Przypisz sugestywny identyfikator wskazujący zawartość wersji wyceny, np. **2016-AKTUALIZACJE**.
-   Upewnij się, że zawartość obejmuje rekordy kosztów.
-   Zezwól na wprowadzanie rekordów kosztów we wszystkich oddziałach. Jeśli określisz oddział, rekordy kosztów można wprowadzić tylko w tym oddziale.
-   W polu zasady alternatywnego źródła ustaw **Brak**. Zasada alternatywnego źródła ma zastosowanie tylko do obliczeń kosztów produkowanych towarów.

Aby skorygować, dopasować lub zaktualizować standardowe koszty nowych towarów, wykonaj następujące czynności.

1.  Na stronie **Konfiguracja wersji** **wyceny** włącz możliwość wprowadzania danych kosztów do drugiej wersji wyceny. Opcjonalnie zablokuj możliwość aktywacji kosztów oczekujących, tak aby aktywacja była dozwolona dopiero po całkowitym i dokładnym zdefiniowaniu tych kosztów. Opcjonalnie można wprowadzić datę w polu **Od dnia**. Określi ona, od kiedy zostaną włączone aktualizacje przyrostowe. Alternatywnie pozostaw niewypełnione pole **Od dnia** w ustawieniach wersji wyceny, a wypełnij pole **Od dnia** w każdym rekordzie kosztu.
2.  Na stronie **Cena pozycji** wprowadź aktualizacje jako rekordy kosztów towarów umieszczone w drugiej wersji wyceny.
3.  Za pomocą raportu **Ceny pozycji** zweryfikuj kompletność i dokładność rekordów kosztów towarów umieszczonych w drugiej wersji wyceny.
4.  Na stronie **Obsługa wersji wyceny** zmień flagę blokowania, aby umożliwić aktywowanie rekordów kosztów oczekujących umieszczonych w drugiej wersji wyceny.
5.  Na stronie **Aktywuj ceny** (którą można otworzyć ze strony **Obsługa wersji wyceny**) aktywuj wszystkie rekordy kosztów oczekujących towarów, jakie znajdują się w drugiej wersji wyceny. Można również aktywować rekordy kosztów oczekujących dla poszczególnych towarów, klikając przycisk **Aktywuj oczekującą cenę** umieszczony na stronie **Cena pozycji**.
6.  Aby uniemożliwić dalsze modyfikowanie, na stronie **Konfiguracja wersji wyceny** zmień flagi blokowania umieszczone w drugiej wersji wyceny. Zasady blokowania zapobiegają wprowadzeniu nowych kosztów oczekujących i aktywowaniu kosztów oczekujących.



