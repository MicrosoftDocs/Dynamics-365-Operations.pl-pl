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

[!include[banner](../includes/banner.md)]




Polecenie zapłaty SEPA służy do gromadzenia środków z konta bankowego odbiorcy przez wierzyciela pod warunkiem, że odbiorca udzielił na to pisemnej zgody wierzycielowi. Odbiorca podpisuje zgodę, która upoważnia wierzyciela do pobierania płatności i instruuje bank odbiorcy, że ma on dokonać wypłaty. Ten temat uporządkowano tak, aby przedstawiał proces konfigurowania zgód na polecenie zapłaty SEPA.

## <a name="prerequisites"></a>Wymagania wstępne
W poniższej tabeli przedstawiono wymagania wstępne, które muszą istnieć przed rozpoczęciem.

| Kategoria       | Wymaganie wstępne                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kraj/region | Adres podstawowy dla firmy musi być w krajach/regionach: Austria, Belgia, Niemcy, Hiszpania, Francja, Włochy lub Holandia. |

1. Konfigurowanie numeracji zgód na polecenie zapłaty Każda zgoda na polecenie zapłaty musi mieć unikatowy numer. Użyj strony **Sekwencje identyfikatorów**, aby utworzyć sekwencję numerów dla zgód na polecenie zapłaty. Użyjesz tego identyfikatora do przypisania sekwencji numerów do systemu zgody na polecenie zapłaty na stronie **Parametry modułu rozrachunków z odbiorcami**.

2. Konfigurowanie parametrów rozrachunków z odbiorcami dla zgód na polecenie zapłaty Na stronie **Parametry modułu rozrachunków z odbiorcami** ustaw parametry zgody na polecenie zapłaty. Aby skonfigurować parametry, na karcie **Polecenie zapłaty** zmień parametry domyślne w żądany sposób. Następnie na karcie **Sekwencje identyfikatorów** zaktualizuj pole **Identyfikator zgody na polecenie zapłaty**, wprowadzając ustawioną wcześniej numerację.

3. Konfigurowanie metod płatności dla zgód na polecenie zapłaty Należy skonfigurować metodę płatności dla zgód na polecenie zapłaty. Tej metody płatności używa się do tworzenia kwerendy na fakturach, dla których mają być wygenerowane płatności przez polecenie zapłaty. Na stronie **Metoda płatności** ustaw metodę płatności. Aby skonfigurować metodę płatności dla zgody na polecenie zapłaty, należy wykonać następujące czynności dodatkowe dla metody płatności:

-   W polu **Typ płatności** wybierz opcję **Płatność elektroniczna**.
-   Opcjonalnie: Jeśli spodziewasz się, że każdy odbiorca będzie miał wiele zgód, w polu **Okres** zaznacz wartość **Faktura**. Dla każdej faktury będzie tworzona osobna płatność, a do każdej płatności będzie wykorzystywana zgoda określona dla faktury.
-   Wybierz opcję **Wymaga zgody**, aby utworzyć płatności za pomocą zgody na polecenie zapłaty. Opcja **Wymaga zgody** jest dostępna tylko w przypadku wybrania opcji **płatności elektronicznych** w polu **Typ płatności**.

Zobacz też [Omówienie polecenia zapłaty](sepa-direct-debit-overview.md) 



