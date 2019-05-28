---
title: Konfigurowanie metody płatności poleceniem zapłaty ISO20022
description: W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 953a3cffc356ab44163944318e7e7d542a113112
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559346"
---
# <a name="setup-method-of-payment-for-iso20022-direct-debit"></a>Konfigurowanie metody płatności poleceniem zapłaty ISO20022

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano, jak skonfigurować metodę płatności od odbiorcy poleceniem zapłaty ISO20022 lub za pomocą innego typu płatności, używając raportowania elektronicznego. 



Przed wykonaniem tego zadania trzeba utworzyć konfiguracje formatów eksportu i konta płatności.



Procedurę utworzono przy użyciu danych firmy demonstracyjnej DEMF.



Jest to trzecia z pięciu procedur, które razem przedstawiają proces płatności od odbiorców przy użyciu konfiguracji raportowania elektronicznego.

1. Wybierz kolejno opcje Rozrachunki z odbiorcami > Ustawienia płatności > Metody płatności.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Metoda płatności z wartością „ELECTRONIC”.
3. Kliknij przycisk Edytuj.
4. W polu Konto płatności wpisz wartość „DEMF OPER”.
5. Rozwiń sekcję Formaty plików.
6. W polu Ogólne raportowanie elektroniczne wybierz opcję Tak.
7. W polu Konfiguracja formatu eksportu wpisz lub wybierz wartość.
    * Na liście zaznacz pozycję Polecenie zapłaty ISO20022 (Niemcy).  Jeśli lista jest pusta, nie istnieje żadna zaimportowana i aktywna konfiguracja formatu eksportu płatności od odbiorcy.  
8. W polu Wymaga zgody wybierz opcję Tak.
    * Wybierz parametr Wymaga zgody dla formatów płatności od odbiorców, które wymagają zawarcia informacji o zgodzie w komunikacie płatności. Dotyczy to na przykład poleceń zapłaty SEPA.  
9. Kliknij przycisk Zapisz.

