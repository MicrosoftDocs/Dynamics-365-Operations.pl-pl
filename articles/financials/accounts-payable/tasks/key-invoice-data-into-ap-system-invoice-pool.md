---
title: Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur
description: W tym przewodniku po zadaniach zostanie pokazane, jak korzystać z rejestru faktur do tworzenia faktur.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b870613512a8f4a5c19a0a05cd72b35ea32861b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843224"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym przewodniku po zadaniach zostanie pokazane, jak korzystać z rejestru faktur do tworzenia faktur.  Następnie pula faktur posłuży dopasowaniu faktury do zamówienia zakupu i sfinalizowaniu wydatku na stronie faktury od dostawcy.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Zamówienia zakupu > Zamówienia zakupu.
2. Kliknij przycisk Nowy, aby utworzyć zamówienie zakupu.
3. W polu Konto dostawcy kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Wybierz dostawcę z listy. Na przykład dostawcę 1001.
5. Kliknij przycisk OK.
6. W polu Numer towaru kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
7. Na liście odszukaj numer towaru będącego usługami. Na przykład zaznacz S0001.
8. Kliknij numer towaru i go zaznacz.
    * Kwota netto wynosi 75,00 zł.  To kwota, której oczekujemy na fakturze.  
9. W okienku akcji kliknij pozycję Zakup.
10. Kliknij przycisk Potwierdź.

## <a name="create-and-post-and-invoice"></a>Tworzenie i księgowanie faktury
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Rejestr faktur.
2. Kliknij przycisk Nowy.
3. Otwórz wyszukiwanie i zaznacz nazwę rejestru faktur, którego chcesz używać.
4. Wybierz nazwę rejestru faktur, którego chcesz używać.
5. Kliknij przycisk Wiersze, aby otworzyć rejestr i wprowadzić wiersze wydatków.
6. W wyszukiwaniu wybierz dostawcę. Na przykład kliknij dostawcę 1001.
7. W polu Faktura wprowadź numer faktury.
8. W polu Opis wpisz wartość.
9. W polu Kredyt wpisz liczbę.
10. W polu Zamówienie zakupu kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Zaznacz utworzone wcześniej zamówienie zakupu.
12. W polu Zatwierdzone przez kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
13. Zaznacz osobę zatwierdzającą i kliknij przycisk Wybierz, aby ją wybrać.
14. Kliknij przycisk Księguj.
15. Zamknij formularz.
16. Zamknij formularz.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Otwieranie faktury z puli i uzgadnianie jej z zamówieniem zakupu w celu dokończenia procesu fakturowania
1. Wybierz kolejno opcje Rozrachunki z dostawcami > Faktury > Pula faktur.
2. Kliknij opcję Zamówienie zakupu, aby utworzyć fakturę od dostawcy na bazie faktury z puli.
3. Wybierz fakturę, którą chcesz przejrzeć.
4. Kliknij przycisk Aktualizuj stan uzgadniania, aby dokończyć uzgadnianie.
5. W okienku akcji kliknij pozycję Opcje.
6. Kliknij przycisk Zmień widok.
7. Kliknij opcję Widok siatki.
8. Kliknij przycisk Księguj.
9. Zamknij formularz.
10. Wybierz kolejno opcje Rozrachunki z dostawcami > Dostawcy > Dostawcy.
11. Zaznacz dostawcę, który figurował w zamówieniu zakupu. Na przykład zaznacz dostawcę 1001.
12. Na liście kliknij łącze w wybranym wierszu.
13. W okienku akcji kliknij pozycję Dostawca.
14. Kliknij opcję Transakcje.
15. Zaznacz utworzoną przez siebie fakturę.
    * Naliczenie w rejestrze faktur zostało wycofane, a następnie zaksięgowane na odpowiednim koncie wydatków.  

