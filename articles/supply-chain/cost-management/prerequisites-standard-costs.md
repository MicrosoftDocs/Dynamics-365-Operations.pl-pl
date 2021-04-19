---
title: Omówienie wymagań wstępnych dotyczących kosztów standardowych
description: W tym temacie opisano podstawowe czynności związane z używaniem kosztów standardowych.
author: AndersGirke
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 92f80ecc611e68210e24e59b696724e1bc9c3a06
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809669"
---
# <a name="prerequisites-for-standard-costs-overview"></a>Omówienie wymagań wstępnych dotyczących kosztów standardowych

[!include [banner](../includes/banner.md)]

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

-  Na karcie **Księgowanie zapasów** dostępnej na stronie **Ustawienia zasad księgowania zapasów > Parametry** zdefiniuj dwa parametry kontroli kosztów powiązane z kosztami standardowymi.

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

### <a name="blogs"></a>Blogi

#### <a name="community-blogs"></a>Blogi społeczności

- [Jak ustawić standardowe koszty w materiałów bezpośrednich w Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [Koszty standardowe bezpośredniej robocizny w Dynamics 365 for Finance and Operations](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]