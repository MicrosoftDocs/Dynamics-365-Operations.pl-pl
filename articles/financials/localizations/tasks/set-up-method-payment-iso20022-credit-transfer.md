---
title: Konfigurowanie metody płatności przelewu ISO20022
description: W tej procedurze pokazano, jak skonfigurować metodę płatności dla dostawcy poleceniem przelewu ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego do wygenerowania pliku.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8bb54864c8d0a57510b4d47b00aed60c5be95512
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1848721"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a>Konfigurowanie metody płatności przelewu ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak skonfigurować metodę płatności dla dostawcy poleceniem przelewu ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego do wygenerowania pliku. 

Przed wykonaniem tego zadania trzeba utworzyć konfiguracje formatów eksportu i konta płatności.

Zadanie utworzono przy użyciu danych firmy demonstracyjnej DEMF.

Jest to trzecia z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Metoda płatności z wartością „SEPA CT”.
3. Kliknij przycisk Edytuj.
4. W polu Okres wybierz opcję „Razem”.
5. W polu Typ płatności wybierz opcję „Płatność elektroniczna”.
6. Rozwiń sekcję Formaty plików.
7. W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.
8. W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.
    * Na liście zaznacz wartość Polecenie przelewu ISO20022 (DE). Jeśli lista jest pusta, nie istnieje żadna zaimportowana i aktywna konfiguracja formatu eksportu płatności dla dostawcy.  
9. W polu Typ konta wybierz opcję „Bank”.
10. W polu Konto płatności wpisz wartość „DEMF OPER”.
11. Kliknij przycisk Zapisz.

