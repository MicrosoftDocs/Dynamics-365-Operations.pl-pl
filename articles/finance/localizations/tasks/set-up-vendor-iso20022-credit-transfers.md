---
title: Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022
description: Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7a901591f9f3d1a892c29f92e59dc96c1f172143cae6bec571da33b4a50d274
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723726"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a>Konfigurowanie dostawców i kont bankowych dostawców dla poleceń przelewu ISO20022

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia sposób konfigurowania dostawcy oraz danych konta bankowego specyficznych dla dostawcy wymaganych do generowania polecenia przelewu ISO20022 lub innego pliku płatności do dostawcy. 

Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej DEMF.
Jest to czwarta z pięciu procedur, które razem ilustrują proces płatności dostawcom przy użyciu konfiguracji raportowania elektronicznego. Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]