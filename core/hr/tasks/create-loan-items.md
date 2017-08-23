--- 
title: "Tworzenie przedmiotów pożyczek"
description: "Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom."
author: kherr75
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 65655283c70c99b5d64289b319ecc69f6e414221
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-loan-items"></a>Tworzenie przedmiotów pożyczek

[!include[task guide banner](../../includes/task-guide-banner.md)]

Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom. Każdy przedmiot fizyczny musi mieć odpowiadający mu przedmiot pożyczki. Każdy rekord przedmiotu pożyczki powinien opisywać wypożyczany przedmiot, osobę odpowiedzialną za wypożyczenie oraz możliwą liczbę dni wypożyczenia przedmiotu. Można utworzyć wiele przedmiotów pożyczki, takich jak klucze, karty dostępu lub mundury, w tym samym czasie. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="create-loan-types"></a>Tworzenie typów pożyczek
1. Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Typy pożyczek.
2. Kliknij przycisk Nowy.
3. W polu Typ pożyczki wpisz wartość.
4. Wypełnij pole Opis.
5. Wprowadź liczbę dni, po upływie których przedmioty przypisane do tego typu pożyczki mogą stanowić zaległość. 
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.
8. Odśwież stronę.

## <a name="create-loan-items"></a>Tworzenie przedmiotów pożyczek
1. Wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Przedmioty pożyczek > Przedmioty pożyczek.
2. Kliknij opcję Tworzenie przedmiotów pożyczek.
3. W polu Ilość wpisz liczbę.
4. Wypełnij pole Opis.
5. W polu Typ pożyczki kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
6. Na liście znajdź i zaznacz odpowiedni rekord.
7. Na liście kliknij łącze w wybranym wierszu.
8. Wprowadź liczbę dni, przez jaką przedmiot może być wypożyczony.
    * Domyślna wartość pola Planowany zwrot na stronie Sprzęt wypożyczony jest obliczana przez dodanie tej liczby do daty bieżącej.  
9. W polu Osoba odpowiedzialna kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
10. Kliknij opcję Wybierz.
11. W polu Wartość początkowa wprowadź liczbę.
12. W polu Interwał wpisz liczbę.
13. W polu Format wpisz wartość.
    * Na przykład jeśli numerem początkowym przedmiotu pożyczki jest 10, wprowadź dwa symbole liczb w polu Format.  
14. Kliknij przycisk OK.
15. Odśwież stronę.


