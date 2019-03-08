---
title: Tworzenie przedmiotów pożyczek
description: Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e17005bda302c58f5a6560fe9c4eda04e918c92f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "341840"
---
# <a name="create-loan-items"></a>Tworzenie przedmiotów pożyczek

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

