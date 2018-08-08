---
title: "Konfigurowanie polecenia zapłaty SEPA"
description: "Polecenie zapłaty SEPA służy do gromadzenia środków z konta bankowego odbiorcy przez wierzyciela pod warunkiem, że odbiorca udzielił na to pisemnej zgody wierzycielowi."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 242d6d3d517ad5190b96ace36bd585a5769ae994
ms.contentlocale: pl-pl
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-sepa-direct-debit-mandate"></a>Konfigurowanie polecenia zapłaty SEPA

[!include [banner](../includes/banner.md)]

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

Dodatkowe zasoby

[Omówienie polecenia zapłaty](sepa-direct-debit-overview.md) 

[Tworzenie pozwolenia na polecenie zapłaty dla odbiorcy](tasks/create-direct-debit-mandate-customer.md) 


