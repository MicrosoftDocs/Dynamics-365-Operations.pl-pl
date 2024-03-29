---
title: Konfigurowanie reguł uzgodnienia konta bankowego
description: W tym artykule objaśniono metody konfigurowania reguł uzgadniania wyciągów bankowych i zestawów tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów bankowych są zbiorem kryteriów, które są używane do filtrowania wierszy wyciągu bankowego i dokumentów bankowych podczas procesu uzgadniania.
author: angelad116
ms.date: 11/22/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: kfend
ms.custom: 12971
ms.assetid: b5073f83-31dc-404f-af42-3fd84a02a7c6
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac5ab5e2bcb9a63bb52d5a74bd5e4b5db51ba603
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803945"
---
# <a name="set-up-bank-reconciliation-matching-rules"></a>Konfigurowanie reguł uzgodnienia konta bankowego

[!include [banner](../includes/banner.md)]

W tym artykule objaśniono metody konfigurowania reguł uzgadniania wyciągów bankowych i zestawów tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów bankowych są zbiorem kryteriów, które są używane do filtrowania wierszy wyciągu bankowego i dokumentów bankowych podczas procesu uzgadniania.

Można skonfigurować reguły uzgadniania wyciągów bankowych i zestawy tych reguł, aby ułatwić uzgadnianie konta bankowego. Reguły uzgadniania wyciągów to zestaw kryteriów, które są używane do filtrowania podczas procesu uzgadniania wierszy wyciągu bankowego z wierszami transakcji bankowych w Dynamics 365 Finance. Użyj strony **reguł uzgadniania wyciągów** w celu ustawienia reguł uzgadniania. Można skonfigurować więcej niż jedną regułę uzgadniania, a następnie utworzyć zestaw reguł uzgadniania na stronie **Zestaw reguł uzgadniania wyciągów bankowych**. 

> [!NOTE] 
> Reguły uzgadniania wyciągów bankowych są używane w przypadku uzgadniania elektronicznego wyciągu bankowego za pomocą zaawansowanego uzgadniania konta bankowego. 

Na stronie **Reguły uzgadniania wyciągów bankowych** można wybrać akcje i kryteria wyboru używane po uruchomieniu reguły uzgadniania. W grupie pól **Akcje** wybierz akcję, która będzie wykonywana po uruchomieniu reguły uzgadniania podczas procesu uzgadniania.  

Domyślnie Dopasowywanie reguł szuka dopasowania do pierwszego dokumentu bankowego spełniającego kryteria reguły uzgadniania. Jeśli wiele dokumentów bankowych spełnia kryteria reguły, parametr, który ma wymagać ręcznego dopasowania, można włączyć, przechodząc do ustawień modułu **Zarządzanie gotówką i bankami > Konfiguracja > Parametry ustawień gotówkowych i bankowych > Uzgodnienia bankowe > Wymagaj ręcznego dopasowania, gdy reguły uzgadniania konta bankowego wyszukają wielu dokumentów pasujących do kwoty**.

> [!NOTE] 
> Wybrana opcja określa wyświetlane pola.

| Akcja | opis   | Kryteria wyboru dostępne po wybraniu akcji     |
|--------|---------------|----------------------------------------------------------|
| **Połącz z dokumentem bankowym**       |  Umożliwia tworzenie kryteriów określania sposobu dopasowywania wierszy wyciągu bankowego i dokumentów bankowych, gdy reguła uzgadniania jest uruchamiana ze strony **Arkusz uzgadniania konta bankowego**. Wiersze transakcji są wybierane według dodatkowych kryteriów skonfigurowanych na skróconych kartach. | <ul><li>**Krok 1: Definiowanie reguły uzgadniania** — wybierz kryteria, aby określić, które wyciągi bankowe mają być dopasowane do transakcji bankowych w Finance.</li><li> **Krok 2 (opcjonalnie): zaznacz wiersze wyciągu do uruchomienia reguły uzgadniania:** zastosuj filtr, aby określić wiersz, w którym mają zostać uruchomione reguły.</li></ul>                                       |
| **Wyczyść wycofane wiersze wyciągu** | Utwórz kryteria kryteriów sposobu określania usuwania wierszy wyciągu ze strony **Arkusz uzgadniania konta bankowego** po uruchomieniu reguły uzgadniania. Ta opcja jest używana, jeśli bank robi błąd i istnieją dwa wiersze wyciągu bankowego wymienione w zaimportowanym wyciągu bankowym, które muszą zostać uzgodnione. |<ul><li> **Krok 1**:**Znajdź wycofane wiersze wyciągu**— dodaj kryteria wyboru wierszy wyciągu bankowego do wycofania. Na przykład, aby zaznaczyć tylko czeki, wybierz opcję **Kod transakcji bankowej** w polu **Pole**, wybierz znak + w polu **Operator**, a następnie wprowadź **Czeki** w polu **Wartości**. </li><li>**Krok 2: Znajdź oryginalne wiersze wyciągu** — umożliwia dodanie kryteriów wyboru przy uzgadnianiu wierszy dokumentów bankowych z wierszami wyciągu bankowego. </li><li>**Krok 3: Znajdź transakcje bankowe w Finance** — umożliwia dodanie kryteriów wyboru przy uzgadnianiu transakcji bankowych w Finance z wierszami wyciągu bankowego.</li></ul>  |
| **Zaznacz nowe transakcje**          | Utwórz kryteria sposobu oznaczania nowych transakcji na stronie **Arkusz uzgadniania konta bankowego** po uruchomieniu reguły uzgadniania.                                                                                                                                                                 | <ul><li>**Krok 1: Znajdź wiersze wyciągu**— dodaj pola wyboru, aby określić, które wiersze wyciągu bankowego powinny zostać zaznaczone na stronie **Arkusz uzgadniania konta bankowego**.</li><li> **Krok 2: Znajdź transakcje bankowe w aplikacjach finansowych i operacyjnych** — umożliwia dodawanie kryteriów wyboru do wyszukiwania wierszy dokumentu bankowego. Jeśli nie zostanie znaleziony żaden dokument bankowy, wiersz wyciągu będzie oznaczony jako nowa transakcja. </li></ul>         |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

