---
title: Zaliczka na podatek w transakcjach zakupu
description: W przypadku dostawców, którzy są objęci potrąconą zaliczką na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Wszyscy dostawcy**.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: faeaf0746532875d3517a208c9c338c112bf2c77
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816890"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Zaliczka na podatek w transakcjach zakupu

W przypadku dostawców, którzy są objęci potrąconą zaliczką na podatek w płatnościach na rzecz użytkownika, można przypisać **Domyślną grupę potrąconej zaliczki na podatek** na stronie **Wszyscy dostawcy**.

1. Przejdź do **Okienko nawigacij > Moduły > Rozrachunki z dostawcami > Dostawcy > Wszyscy dostawcy**.

2. Kliknij odpowiednie konto dostawcy i kliknij przycisk **Edytuj**.

3. Na karcie **Faktura i dostawa** w polu **Oblicz potrącanie zaliczki na podatek** ustaw wartość **Tak**.

   > [!NOTE] 
   > Podatek u źródła nie zostanie obliczony, jeśli **Obliczanie zaliczki na podatek** nie jest włączone dla tego dostawców w danych.

4. Wybierz grupę Potrącona zaliczka na podatek na liście **Grupa potrąconej zaliczki na podatek**.

5. Kliknij przycisk **Zapisz**.

W przypadku towarów / usług, które podlegają potrąceniu u źródła, można przypisać domyślną **Grupę podatku potrącanego u źródła** w obszarze **Zwolnione produkty**.

1. Otwórz **Okienko nawigacji > Moduły > Informacje o zarządzaniu produktem > Produkty > Wydane produkty**.

2. Kliknij odpowiedni numer pozycji i kliknij przycisk **Edytuj**.

3. Na karcie **Zakup** kliknij przycisk **Oblicz potrącenie zaliczki na podatek**.

   > [!NOTE] 
   > Potrącona zaliczka na podatek nie zostanie obliczona, jeśli ustawienie **Oblicz potrąconej zaliczki na podatek** nie ma wartości **Tak** dla tej pozycji na karcie **Zakup** na stronie **Zwolniony produkt**.

4. Wybierz grupę Potrącona zaliczka na podatek od pozycji na liście **Grupa potrąconej zaliczki na podatek od pozycji**.

5. Kliknij przycisk **Zapisz**.

Można przypisać grupy potrąconych zaliczek na podatek i grupy potrąconych zaliczek na podatek od pozycji na stronach: 

- **Zamówienie zakupu**
- **Faktura dostawcy**
- **Arkusz faktur**

Domyślna grupa potrąconej zaliczki na podatek i grupa potrąconej zaliczki na podatek od pozycji zostaną włączone do wierszy podczas tworzenia **Zamówień zakupu** i/lub **Faktur oczekujących dostawców**. Dla **Arkusz faktur od dostawców** można włączyć **Oblicz potrącenie zaliczki na podatek** i wybrać **Grupa potrąconej zaliczki na podatek od pozycji** na karcie **Ogólne** w arkuszu.

Tymczasowa kwota potrąconej zaliczki na podatek jest dostępna w polu **Skorygowana potrącona zaliczka na podatek** na karcie **Sumy** na stronie **Zamówienie zakupu**.

![Potrącona zaliczka na podatek jest uwzględniona w zamówieniu zakupu](media/withholding-tax-adjusted.png)

Potrącona zaliczka na podatek jest obliczana na podstawie **Arkusz płatności dostawców**. Można ręcznie skorygować stosowane kody potrąconej zaliczki na podatek oraz rzeczywistą kwoty potrąconej zaliczki na podatek na karcie **Potrącona zaliczka na podatek** na stronie **Rozlicz transakcje**.

![Potrącenie można ręcznie skorygować na stronie Rozlicz transakcje](media/withholding-tax-vendor-payment-tab.png)

Uzyskana kwota podatku potrąconego u źródła zostanie odjęta od płatności dostawcy i zaksięgowana na koncie **Potrąconej zaliczki na podatek** w powiązanym załączniku.

![Konto potrąconej zaliczki na podatek pokazujące powiązany załącznik](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]