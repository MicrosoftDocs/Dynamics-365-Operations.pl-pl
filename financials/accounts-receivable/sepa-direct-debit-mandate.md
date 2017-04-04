---
title: "Skonfiguruj zgodę na polecenie zapłaty SEPA"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Skonfiguruj zgodę na polecenie zapłaty SEPA



Polecenie zapłaty SEPA służy do gromadzenia środków z konta bankowego odbiorcy przez wierzyciela pod warunkiem, że odbiorca udzielił na to pisemnej zgody wierzycielowi. Odbiorca podpisuje zgodę, która upoważnia wierzyciela do pobierania płatności i instruuje bank odbiorcy, że ma on dokonać wypłaty. W tym temacie jest zorganizowana do przedstawiania procesu ustalania do zapłaty SEPA.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Kategoria       | Wymaganie wstępne                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kraj/region | Adres podstawowy dla firmy musi być w krajach/regionach: Austria, Belgia, Niemcy, Hiszpania, Francja, Włochy lub Holandia. |

1. Konfigurowanie sekwencji numerów dla zapłaty każdego polecenie zapłaty musi mieć unikatowy numer. Użyj strony **Sekwencje identyfikatorów**, aby utworzyć sekwencję numerów dla zgód na polecenie zapłaty. Użyjesz tego identyfikatora do przypisania sekwencji numerów do systemu zgody na polecenie zapłaty na stronie **Parametry modułu rozrachunków z odbiorcami**.

2. Konfigurowanie parametrów rozrachunków z odbiorcami dla zapłaty wykorzystania **rozrachunków z odbiorcami Parametry** stronę do ustawiania parametrów dla zapłaty. Umożliwia ustawianie parametrów, na **zapłaty** karta, zmiany parametrów domyślnych, ile jest potrzebnych. Następnie, na **sekwencje numerów** tab, aktualizacja **identyfikator polecenia zapłaty mandatu** pola z sekwencji numerów, który został ustawiony wcześniej.

3. Ustawianie metody płatności dla mandatów zapłaty, możesz należy zdefiniować metodę płatności do zapłaty. Tej metody płatności używa się do tworzenia kwerendy na fakturach, dla których mają być wygenerowane płatności przez polecenie zapłaty. Na stronie **Metoda płatności** ustaw metodę płatności. Aby skonfigurować metodę płatności dla zgody na polecenie zapłaty, należy wykonać następujące czynności dodatkowe dla metody płatności:

-   W polu **Typ płatności** wybierz opcję **Płatność elektroniczna**.
-   Opcjonalnie: Jeśli oczekujesz, każdy klient ma wiele mandatów, w **okresu** pól, zaznacz **faktury**. Będzie można utworzyć osobną płatność dla każdej faktury, a każda płatność użyje mandatu, która jest określona dla faktury.
-   Wybierz opcję **Wymaga zgody**, aby utworzyć płatności za pomocą zgody na polecenie zapłaty. Opcja **Wymaga zgody** jest dostępna tylko w przypadku wybrania opcji **płatności elektronicznych** w polu **Typ płatności**.

Zobacz też [omówienie zapłaty](sepa-direct-debit-overview.md) 

