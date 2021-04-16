---
title: Tworzenie przedmiotów pożyczek
description: Przedmioty pożyczek są rekordami, które pomagają śledzić fizyczne przedmioty, takie jak telefony lub komputery, które firma pożycza pracownikom.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 28fb201f7951384d847058b05668a7f3e366700a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800244"
---
# <a name="create-loan-items"></a>Tworzenie przedmiotów pożyczek

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



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



[!INCLUDE[footer-include](../includes/footer-banner.md)]