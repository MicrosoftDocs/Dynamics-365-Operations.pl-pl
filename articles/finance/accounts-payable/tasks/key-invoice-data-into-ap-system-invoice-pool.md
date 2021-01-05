---
title: Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur
description: W tym temacie opisano sposób używania rejestru faktur do tworzenia faktur.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
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
ms.openlocfilehash: cd6de42dda650d42d703e905f8d48f73b9e4afd6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446746"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Wprowadzanie najważniejszych danych faktury do modułu rozrachunków z dostawcami za pomocą puli faktur

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób używania rejestru faktur do tworzenia faktur. Następnie pula faktur posłuży dopasowaniu faktury do zamówienia zakupu i sfinalizowaniu wydatku na stronie faktury od dostawcy.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Zamówienia zakupu**.
2. Kliknij przycisk **Nowe**, aby utworzyć nowe zamówienie zakupu.
3. W polu **Konto dostawcy** otwórz listę rozwijaną, aby wybrać dostaawcę. Na przykład zaznacz dostawcę **1001**.
4. Kliknij przycisk **OK**.
5. W polu **Numer produktu** wybierz odpowiedni numer produktu z listy rozwijanej. Na przykład zaznacz **S0001**. Kwota netto wynosi 75,00 zł.  To kwota, której oczekujemy na fakturze.  
6. W okienku akcji wybierz pozycję **Zakup**.
7. Wybierz opcję **Potwierdź**.

## <a name="create-and-post-and-invoice"></a>Tworzenie i księgowanie faktury
1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Rejestr faktur**.
2. Wybierz pozycję **Nowy**.
3. Otwórz wyszukiwanie i zaznacz nazwę rejestru faktur, którego chcesz używać.
4. Wybierz nazwę rejestru faktur, którego chcesz używać.
5. Kliknij przycisk **Wiersze**, aby otworzyć rejestr i wprowadzić wiersze wydatków.
6. W wyszukiwaniu wybierz dostawcę. Na przykład zaznacz dostawcę **1001**.
7. W polu **Faktura** wprowadź numer faktury.
8. W polu **Opis** wpisz wartość.
9. W polu **Kredyt** wpisz liczbę.
10. W polu **zamówienie zakupu** otwórz listę rozwijaną, aby wybrać utworzone wcześniej zamówienie zakupu.
11. W polu **zatwierdzone przez** wybierz pozycję osoba zatwierdzająca z listy rozwijanej i kliknij przycisk **wybierz**, aby wybrać tę osobę zatwierdzającą.
12. Wybierz opcję **Zaksięguj**.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Otwieranie faktury z puli i uzgadnianie jej z zamówieniem zakupu w celu dokończenia procesu fakturowania
1. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Faktury > Pula faktur**.
2. Kliknij opcję **Zamówienie zakupu**, aby utworzyć fakturę od dostawcy na bazie faktury z puli.
3. Wybierz fakturę, którą chcesz przejrzeć.
4. Kliknij **Aktualizuj stan uzgadniania**, aby dokończyć uzgadnianie.
5. W okienku akcji kliknij pozycję **Opcje**.
6. Wybierz **Zmień widok**.
7. Wybierz **Widok siatki**.
8. Wybierz opcję **Zaksięguj**.
9. Zamknij formularz.
10. W okienku nawigacji przejdź do **Moduły > Rozrachunki z dostawcami > Dostawcy > Dostawcy**.
11. Zaznacz dostawcę, który figurował w zamówieniu zakupu. Na przykład zaznacz dostawcę **1001**.
12. W okienku akcji wybierz pozycję **Dostawca**.
13. Wybierz **transakcje**.
14. Zaznacz utworzoną przez siebie fakturę. Naliczenie w rejestrze faktur zostało wycofane, a następnie zaksięgowane na odpowiednim koncie wydatków.  

