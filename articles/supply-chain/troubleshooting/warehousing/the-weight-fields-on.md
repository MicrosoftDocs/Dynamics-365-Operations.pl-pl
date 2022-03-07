---
title: Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku
description: Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924358"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku

Kody błędu: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Objawy

W systemie wyświetlany jest następujący komunikat o błędzie:

> Pola wagi w wierszach ładunku nie pasują do pól wagi w ładunku %1. Uruchom proces Sprawdzenie spójności wagi ładunku magazynu w celu ponownego przeliczenia pól wagi.

## <a name="cause"></a>Powód

Pola **Waga netto** i **Tara** w wierszu ładunku mają wartość *0* (zero). Jednak w polach wagi nie są ustawiane wartości *0* jako miary wagi produktu. Jeśli pola wagi nie są ustawione w wierszu ładunku, korekty ilości w wierszu ładunku mogą powodować niepoprawne obliczenie wagi w ładunku. Ten problem może wystąpić, jeśli wagi produktu zostały zmienione od czasu utworzenia wiersza ładunku.

## <a name="resolution"></a>Rozdzielczość

Domyślnie podczas tworzenia wiersza ładunku są w nim wstawiane pola wagi z produktu. Jeśli waga wynosi zero, można ją ponownie przeliczyć za pomocą funkcji *Sprawdzenia spójności wagi ładunku magazynu*.

1. Przejdź do okna **Administracja systemu \> Okresowe zadania \> Baza danych \> Sprawdzania spójności**.
1. W oknie dialogowym **Sprawdzanie spójności** ustaw pole **Moduł** na *Zarządzanie magazynem*.
1. Ustaw pole **Sprawdź/napraw** na *Naprawić błąd*.
1. Na liście pól wyboru zaznacz pole wyboru **Sprawdzenie spójności wagi ładunku magazynu** i upewnij się, że podświetlony zostanie tylko wiersz tego pola wyboru.
1. Na początku listy pól wyboru naciśnij przycisk wielokropka (**...**), a następnie wybierz opcję **Okno dialogowe** w menu.
1. W oknie dialogowym **Sprawdzenie spójności wagi ładunku magazynu** skonfiguruj następujące pola, aby określić kryteria, dla których ma być uruchamiane sprawdzanie spójności:

    - **Identyfikator ładunku:** określ identyfikator ładunku. Aby sprawdzać wszystkie identyfikatory ładunku, należy pozostawić to pole puste.
    - **Numer towaru:** umożliwia określenie numeru towaru. Aby sprawdzać wszystkie towary, należy pozostawić to pole puste.
    - **Zawsze ponownie oblicz wagę ładunków:** ustaw tę opcję na wartość *Tak*.
    - **Zezwalaj na zastępowanie wagi w wierszach ładunku:** ustaw tę opcję na *Tak*.

1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe **Sprawdzenie spójności wagi ładunku magazynu**.
1. Naciśnij przycisk wielokropka, a następnie wybierz polecenie **Wykonaj** w menu.

Waga zostanie przeliczona na podstawie podanych kryteriów. Wybierz łącze **Szczegóły komunikatu**, aby wyświetlić wynik sprawdzania spójności.
