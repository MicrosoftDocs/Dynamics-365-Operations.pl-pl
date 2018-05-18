---
title: "Wymagania wstępne dotyczące konwersji na koszt standardowy"
description: "W tym temacie omówiono zadania do wykonania przed dokonaniem konwersji na koszt standardowy."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 65844bd78363dc6638b16b3fd4ca163a3fde6a23
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="prerequisites-for-a-standard-cost-conversion"></a>Wymagania wstępne dotyczące konwersji na koszt standardowy

[!include [banner](../includes/banner.md)]

W tym temacie omówiono zadania do wykonania przed dokonaniem konwersji na koszt standardowy. 

Przed dokonaniem konwersji na koszt standardowy wykonaj następujące kroki:

1.  Zdefiniuj **grupę modeli pozycji** dla kosztów standardowych. Użyj strony grupy modeli pozycji do utworzenia grupy modeli pozycji zawierającą model magazynu z kosztem standardowym. Podczas konfigurowania konwersji na koszt standardowy ta grupa modeli pozycji zostanie przypisana do konwertowanych pozycji.
2.  Przypisz **grupę kosztów** do każdej pozycji.
    -   Grupa kosztów, która jest przypisana do zakupionego towaru, może stanowić podstawę do przypisywania kont księgowych, które są związane z kosztami standardowymi. Dotyczy to także przypisywania kont księgowych na potrzeby odchyleń cen zakupu. W środowisku produkcyjnym grupa kosztów przypisana do zakupionych składników umożliwia także segmentację obliczonych kosztów wytworzonych towarów.
    -   Grupa kosztów przypisana do wytworzonego towaru może stanowić podstawę przypisywania kont księgowych powiązanych z kosztami standardowymi, np. przypisywania kont księgowych do zmian produkcyjnych.

3.  Przypisz **standardową ilość towaru** do wytworzonego towaru, jeśli koszty tego towaru są stałe. Standardowa ilość zamówienia na wytworzony towar ma funkcję księgowej wielkości partii do amortyzacji (lub określenia proporcjonalnego) kosztów stałych, takich jak czasy konfiguracji w operacjach marszruty lub stała ilość składnika na liście BOM.
4.  Przypisz **konta księgi głównej** powiązane z kosztami standardowymi, szczególnie zmienność przeszacowania. Na stronie **Księgowanie** (**Zarządzanie zapasami** &gt; **Ustawienia**) przypisz konta księgi głównej powiązane z kosztami standardowymi. Niezbędnym minimum w procesie konwertowania na koszt standardowy jest przypisanie konta odchylenia przeszacowania dla wszystkich towarów i wszystkich grup kosztów. Na stronie **Plan kont** zdefiniuj konta księgi głównej niezbędne dla kosztów standardowych. Na stronie **Kombinacje transakcji** włącz funkcję relacji kosztowych (dla tabel, grup i wszystkich elementów), zanim zdefiniujesz zasady księgowania pozycji.
5.  Zdefiniuj parametry zapasów związane z kosztami standardowymi. Na karcie **Sekwencje numerów** na stronie **Parametry modułu Zarządzanie zapasami i magazynem** przypisz kolejne numery do załączników przeszacowania. Załącznik przeszacowania jest generowany, gdy konwersja na koszt standardowy skutkuje zmianą wartości magazynowej towaru. Na stronie **Parametry modułu Zarządzanie zapasami i magazynem** zdefiniuj parametry kontroli kosztów (na karcie **Księgowanie zapasów**) w celu zdefiniowania dwóch parametrów powiązanych z kosztami standardowymi.
    -   W polu **Podział kosztów** wybierz lub Nr lub Księga podrzędna. Wybranie opcji Księga podrzędna nosi nazwę aktywnego rozbicia kosztów. Aktywne rozbicie kosztów ma kluczowe znaczenie w obliczaniu, zachowywaniu i wyświetlaniu podziału grupy kosztów w wielopoziomowej strukturze produktów dla towarów, którym przypisano koszt standardowy. Jeśli rozbicie kosztów jest aktywne, można raportować i analizować na jednym poziomie, na wielu poziomach lub w formacie sumarycznym następujące elementy:
        1.  Zapasy
        2.  Praca w toku
        3.  Koszt sprzedanych towarów przypadający na grupę kosztów

        Aktywne rozbicie kosztów oznacza, że włączenie kosztu wytworzonego towaru spowoduje zapisanie podziału grupy kosztów w rekordzie kosztu towaru. Jeśli w polu **Podział kosztów** nie zostanie wybrana żadna opcja, podział grupy kosztów nie zostanie zachowany w wypadku towarów, którym przypisano koszty standardowe. Oznacza to, że koszt standardowy wytworzonego towaru będzie obliczany i zachowywany jako jedna kwota bez podziału grup kosztów, a udział kosztów wytworzonych składników będzie obliczany jako jedna kwota.
    -   Pole **Odchylenia od standardu** służy do wybierania, czy odchylenia mają być sumowane czy określane według grup kosztów. Wybór obsługi według grup kosztów umożliwia identyfikowanie odchyleń cen zakupu i odchyleń produkcji według grup kosztów. Umożliwia to również identyfikowanie czterech typów odchyleń produkcji (odchyleń rozmiaru partii, ilości, ceny i podstawiania). Wybór opcji sumowania oznacza, że nie można identyfikować odchyleń według grup kosztów ani czterech typów odchyleń produkcji. Można wyświetlać tylko podsumowanie odchylenia produkcji. Zasady zamiany odchyleń wartości standardowych działają niezależnie od zasad podziału kosztów, tj. można nie wybrać żadnej zasady podziału kosztów i wybrać takie odchylenia na grupę kosztów, aby nadal były rejestrowane odchylenia produkcyjne na grupę kosztów.






