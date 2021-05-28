---
title: Obliczanie TDS dla faktur
description: Ten temat zawiera odwołanie do transakcji, w których podatek potrącony w źródle (TDS) jest obliczany na poziomie faktury.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 496e87e3028025f738d2f0a697d91c18b77ad1c9
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023512"
---
# <a name="tds-calculation-on-invoices"></a>Obliczanie TDS dla faktur

[!include [banner](../includes/banner.md)]

Ten temat zawiera odwołanie do transakcji, w których podatek potrącony w źródle (TDS) jest obliczany na poziomie faktury.

| Numer seryjny | Typ transakcji                                 | Kwota transakcji | Nazwa strony i ścieżka wyboru                                 | Typ konta i typ konta przeciwstawnego                         |
| ------------- | ------------------------------------------------ | ------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1.            | Zakup dokonany od dostawcy/z rejestrowaniem wydatków   | Debet czy Kredyt  | Strona Arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza zatwierdzania faktur (Rozrachunki z dostawcami > Faktury > Zatwierdzenie faktury), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur) | Dostawca (dr.), dostawca (Cr.).  Potrącona zaliczka na podatek jest obliczana dla kombinacji Dostawca-Księga tylko wtedy, gdy konto księgowe ma typ księgowania **Zakup** **gotówką**. |
| 2.            | Zakup dokonany od odbiorcy/z rejestrowaniem wydatków | Debet czy Kredyt  | Strona arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur) | Dostawca (Dr.), odbiorca (Cr.)                                 |
| 3.            | Zakup środka trwałego od dostawcy              | Debet czy Kredyt  | Strona Arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza rejestru faktur (Rozrachunki z dostawcami > Faktury > Rejestr faktur), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur) | Środki trwałe (Dr.) Dostawca (Cr.)                             |
| 4.            | Zakup środka trwałego od odbiorcy            | Debet czy Kredyt  | Strona arkuszy finansowych (Księga główna > Wpisy w arkuszu > Arkusze finansowe), strona arkusza faktur (Rozrachunki z dostawcami > Faktury > Arkusz faktur) | Środki trwałe (Dr.) Odbiorca (Cr.)                           |
| 5.            | Faktura zakupu (TDS zobowiązań)                  |                    | Strona zamówienia zakupu (Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu) |                                                              |
| 6.            | Faktura sprzedaży (należności TDS)                  |                    | Strona zamówienia sprzedaży (Rozrachunki z odbiorcami > Zamówienia > Wszystkie zamówienia sprzedaży), strona faktury elektronicznej (Rozrachunki z odbiorcami > Faktury > Wszystkie faktury niezależne) |                                                              |
