---
title: "Wymagania wstępne dla kosztów standardowych"
description: "W tym temacie opisano podstawowe czynności związane z używaniem kosztów standardowych."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e63f2b4289b640e601492425331ea8f3804d139a
ms.openlocfilehash: 4f505a2de89863d1a12d415795fdfb82b3557bc0
ms.contentlocale: pl-pl
ms.lasthandoff: 01/17/2018

---

# <a name="prerequisites-for-standard-costs"></a>Wymagania wstępne dla kosztów standardowych

[!include[banner](../includes/banner.md)]


W tym temacie opisano podstawowe czynności związane z używaniem kosztów standardowych. Kolejne czynności zależą od specyfiki działalności firmy. Na przykład są inne dla środowiska nieprodukcyjnego, środowiska produkcyjnego bez marszrut oraz środowiska produkcyjnego wykorzystującego marszruty. 

Aby skonfigurować koszty standardowe, należy wykonać następujące czynności.

**1. Utwórz grupę modeli pozycji opartą na kosztach standardowych.**

Na stronie **Grupy modeli pozycji** utwórz nową grupę dla kosztów standardowych oraz przypisz jej model zapasów **Koszt standardowy**. Identyfikator grupy modeli pozycji powinien być jednoznaczny, np. **Koszt standardowy**. Zaznacz odpowiednie pola wyboru, aby grupa zezwalała na ujemne wartości zapasów finansowych oraz wymuszała księgowanie zapasów fizycznych i finansowych. Ta grupa kosztów standardowych zostanie przypisana do towarów.

**2. Zdefiniuj konta księgowe skojarzone z odchyleniami kosztu standardowego.** 

Strona **Plan kont** służy do definiowania kont księgowych skojarzonych z odchyleniami kosztu standardowego. Te konta księgowe należy zdefiniować przed ich przypisaniem na stronie **Księgowanie**. Konta księgowe mogą uwzględniać grupy towarów i grupy kosztów.

**3. Przypisz konta księgowe do księgowań pozycji (towarów) skojarzonych z odchyleniami kosztu standardowego.** 

Strona **Księgowanie** służy do przypisywania kont księgowych skojarzonych z odchyleniami kosztu standardowego. Można zdefiniować konto księgowe odchyleń według towaru (lub grupy towarów) i według grupy kosztów (lub typu grupy kosztów) albo określić, że konto księgowe dotyczy wszystkich towarów oraz wszystkich grup kosztów. Te opcje odpowiadają relacjom kosztów dla tabel, grup i wszystkich elementów. 

Zanim zdefiniujesz zasady księgowania pozycji, na stronie **Kombinacje transakcji** włącz funkcję relacji kosztowych (dla tabel, grup i wszystkich elementów).

**4. Zdefiniuj parametry zapasów skojarzone z kosztami standardowymi.** 

-  Na stronie **Parametry zapasów** na karcie **Listy składowe (BOM)** zdefiniuj dwa parametry kontroli kosztów powiązane z kosztami standardowymi. 

    -  W polu **Podział kosztów** wybierz opcję **Brak** lub **Księga podrzędna**. W przypadku wybrania opcji **Księga podrzędna** podziałem kosztów jest *aktywny* podziału kosztów. Aktywne rozbicie kosztów ma kluczowe znaczenie w obliczaniu, zachowywaniu i wyświetlaniu podziału grupy kosztów w wielopoziomowej strukturze produktów dla towarów, którym przypisano koszt standardowy. Jeśli podział kosztów jest aktywny, można raportować oraz analizować zapasy, pracę w toku i koszt własny sprzedaży przypadający na grupę kosztów na jednym poziomie, na wielu poziomach lub w formacie sumarycznym. Jeśli podział kosztów jest aktywny, aktywowanie kosztu wytworzonego towaru spowoduje zapisanie segmentacji grupy kosztów w rekordzie kosztu towaru. 

    -  W przypadku wybrania wartości **Brak** segmentacja grupy kosztów nie będzie przechowywana dla towarów opartych na kosztach standardowych. Innymi słowy koszt standardowy wytworzonego towaru będzie obliczany i zachowywany jako jedna kwota, bez segmentacji grup kosztów. Udział kosztów wytworzonych składników będzie obliczany jako jedna kwota.

-  W polu **Odchylenia od standardu** wybierz opcję **Podsumowane** lub **Na grupę kosztów**. Wybór opcji **Na grupę kosztów** umożliwi identyfikowanie odchyleń cen zakupu i odchyleń produkcji według grup kosztów. Można także zidentyfikować cztery typy odchyleń produkcji: wielkości partii, ilości, ceny i podstawiania. Wybór opcji **Podsumowane** spowoduje, że nie będzie można identyfikować odchyleń według grup kosztów ani czterech typów odchyleń produkcji. Można tylko wyświetlać podsumowanie odchylenia produkcji.

-  Zasady zamiany odchyleń wartości standardowych działają niezależnie od zasad podziału kosztów, tj. Innymi słowy można wybrać zasadę podziału kosztów **Brak** i następnie wybrać odchylenia według grup kosztów, aby nadal były rejestrowane odchylenia produkcyjne z podziałem na grupy kosztów.

**5. Utwórz wersje wyceny oparte na kosztach standardowych.** 

Na stronie **Konfiguracja wersji wyceny** można utworzyć jedną lub więcej wersji wyceny opartych na kosztach standardowych. Każda wersja wyceny musi mieć ustawiony typ wyceny **Kosz standardowy** i zezwalać na obecność danych kosztów w zawartości.

**6. Przygotuj istniejącego odbiorcę do używania kosztów standardowych.** 

Odbiorcy, którzy chcą przestawić istniejące towary na model zapasów z kosztem standardowym, muszą w tym celu użyć strony **Konwersje na koszt standardowy**.


<a name="related-topics"></a>Powiązane tematy
--------

[Omówienie konwersji na koszt standardowy](standard-cost-conversion-overview.md)


