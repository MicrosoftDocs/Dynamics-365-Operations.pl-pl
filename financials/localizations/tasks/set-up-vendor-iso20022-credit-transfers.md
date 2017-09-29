--- 
title: "Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022"
description: "Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 147d8fa82bf15c984ad263cada42789038fa7371
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.
Jest to czwarta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="set-up-bank-details"></a>Konfigurowanie danych banku
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawy.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Konto dostawcy z wartością „DE-001”.
3. Kliknij pozycję DE-001, aby otworzyć szczegóły dostawcy.
4. W okienku akcji kliknij pozycję Dostawca.
5. Kliknij przycisk konta bankowe
6. Kliknij przycisk Edytuj.
    * Jeśli konto bankowe nie jest dostępne, należy utworzyć nowe.  
7. W polu Kod SWIFT wpisz wartość „COBADEFFXXX”.
8. W polu IBAN wpisz wartość „DE36200400000628808808”.
9. Zamknij stronę.

## <a name="set-up-a-method-of-payment-for-the-vendor"></a>Konfigurowanie metody płatności dla dostawcy
1. Kliknij przycisk Edytuj.
2. Rozwiń lub zwiń sekcję Płatność.
3. W polu Metoda płatności kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Na liście kliknij łącze w wierszu SEPA CT.
5. Kliknij przycisk Zapisz.

