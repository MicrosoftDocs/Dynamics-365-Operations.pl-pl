---
title: Limity składowania w lokalizacji
description: W tym temacie opisano funkcje limitów składowania w lokalizacji.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: e0adb9d05f0db9bbfe6bfbe72564a4e5e839f163
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004583"
---
# <a name="location-stocking-limits"></a>Limity składowania w lokalizacji

[!include [banner](../includes/banner.md)]

Na stronie **Limity składowania w lokalizacji** (**Zarządzanie magazynem \> Konfiguracja \> Magazyn \> Limity składowania w lokalizacji**) można kontrolować obciążenie pojemności lokalizacji magazynowych bez konieczności używania bardziej zaawansowanych procesów do obliczania objętości fizycznych produktów.

Limity składowania w lokalizacji służą do oceny maksymalnej ilości, jaką może pomieścić lokalizacja. Funkcję tę można skonfigurować na każdym z trzech poziomów, które mają własne karty na stronie **limity składowania w lokalizacji**:

- Produkty
- Warianty produktu
- Typy kontenerów

Na każdym poziomie można zdefiniować inne wartości pól. System będzie wówczas oceniał pojemność określonej lokalizacji na podstawie wartości **Ilość** i **Jednostka** w każdym wierszu. Najpierw zostanie wybrany najbardziej szczegółowy pasujący rekord. Na przykład wiersz, który ma wartość w polu **Identyfikator profilu lokalizacji**, zostanie oceniony przed wierszem mającym wartość tylko w polu **Magazyn**. System oceni także pozostałą pojemność, wykorzystując do tego wartość **Ilość** używanego rekordu limitu składowania w lokalizacji.

W sekcji **Produkty** można określić wartości następujących pól na potrzeby szukania limitów składowania w lokalizacji:

- Magazyn
- Identyfikator profilu lokalizacji
- Lokalizacja
- Identyfikator kategorii wielkości pakunków
- Numer towaru
- Jednostka

> [!NOTE]
> Nie trzeba określać wartości **Jednostka** dla każdego rekordu limitu składowania lokalizacji. Pojemność lokalizacji będzie obliczana na podstawie ilości jednostek magazynowych. Jeśli używana wartość nie ma zdefiniowanej konwersji jednostek, rekord limitu składowania w lokalizacji zostanie pominięty, tak jakby została dla niego zdefiniowana inna wartość **Numeru towaru**.

## <a name="example--purchase-order-receiving"></a>Przykład: przyjęcie zamówienia zakupu

Ten przykład jest oparty na czystym demonstracyjnym zestawie danych firmy *USMF*, w którym na karcie **Warianty produktu** na stronie **Limity składowania w lokalizacji** podano poniższe wartości.

| Magazyn | Identyfikator profilu lokalizacji | Numer towaru | Rozmiar | Ilość | Jednostka |
|-----------|---------------------|-------------|------|----------|------|
| 24        | FLOOR               | D0013       | P    | 300      | Szt.   |
| 24        | FLOOR               | D0013       | L    | 240      | Szt.   |
| 24        | FLOOR               | D0013       | N    | 360      | Szt.   |

Dla produktów skonfigurowano warianty różniące się jednostkami miary. Te warianty są przyporządkowane do limitów składowania w lokalizacji trzech palet (PL):

- **Rozmiar M:** 1 PL = 100 każdego (Ea)
- **Rozmiar L:** 1 PL = 80 Ea
- **Rozmiar S:** 1 PL = 120 Ea

Z tego wynika, że każda lokalizacja, której wartość **Identyfikator profilu lokalizacji** jest ustawiona na *FLOOR*, pomieści *3* *PL* towaru o numerze *D0013*.

### <a name="prepare-for-the-example"></a>Przygotowanie do przykładu

W ramach tego przykładu wygenerujesz przepływ przyjęcia zamówienia zakupu o dwóch wierszach. Wpierw należy jednak zaktualizować dane demonstracyjne w sposób opisany poniżej, by lokalizacje mogły przechowywać mieszane towary, podczas przepływu były używane tylko puste lokalizacje od *FL-002* do *FL-004* i nie było żadnych otwartych prac przychodzących.

1. W przypadku lokalizacji *FL-001* zmień wartość pola **Profil lokalizacji** z *FLOOR* na *FLOOR-05*.
1. W profilu lokalizacji *FLOOR* zmień opcję **Zezwalaj na towary mieszane** na *Tak*.
1. Stwórz zamówienie zakupu z następującymi dwoma wierszami.

    | Magazyn | Numer towaru | Rozmiar | Ilość | Jednostka |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | N    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Przetwarzanie przykładu

Najpierw przyjmij *4* jednostki *PL* rozmiaru *S* i przejrzyj lokalizacje wierszy odłożenia utworzonej pracy. Potem przyjmij *4* jednostki *PL* rozmiaru *L* i przejrzyj lokalizacje wierszy odłożenia utworzonej pracy.

1. Zaloguj się do aplikacji magazynu, podając identyfikator użytkownika *24* i hasło *1*.
1. Wybierz **Przychodzące** \> **Przyjęcia zakupu**.
1. Przyjmij *4* *PL* rozmiaru *S* z towarem o numerze *D0013*.
1. Przejrzyj utworzoną pracę odłożenia. Wynik powinien być następujący:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Przyjmij *4* *PL* rozmiaru *L* z towarem o numerze *D0013*.
1. Przejrzyj utworzoną pracę odłożenia. Wynik powinien być następujący:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

Na podstawie wyników możesz uznać, że system nie przydzielił prawidłowych lokalizacji umieszczenia. Jak inaczej wytłumaczyć fakt, że w ostatnim kroku do lokalizacji *FL-003* system dodał tylko *1* *PL* rozmiaru *L* zamiast *2* *PL*? Tj. dlaczego nie ma łącznie *3* *PL* do odłożenia w tej lokalizacji?

Aby wyjaśnić ten pozorny błąd, należy poznać kryteria wyboru limitów składowania w lokalizacji. System wybiera najbardziej szczegółowy pasujący rekord. W tym przykładzie najbardziej szczegółowym pasującym rekordem jest wiersz, w którym wartość **Rozmiar** to *L*, wartość **Ilość** wynosi *240*, a wartość **Jednostka** to *Ea*. Ponieważ wciąż masz otwartą pracę z poprzedniego przyjęcia *Ea* rozmiaru *S* w ilości *120*, pozostała pojemność została obliczona w następujący sposób: *240* – *120* = *120* *Ea*. W związku z tym pozostała pojemność pozwala dodać jedynie *1* *PL* zawierającą *80* *Ea*.

> [!NOTE]
> Nie można użyć limitów składowania w lokalizacji, by kontrolować na przykład uzupełnianie zapasów towarów, które mają różne ilości w tej samej lokalizacji. W takim wypadku należy zastosować *szablon uzupełnienia zapasów*.
