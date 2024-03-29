---
title: Konfigurowanie udostępnionych parametrów
description: W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c0d8dbca302d90cc402feb4715a6fcc2b935d8b1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906190"
---
# <a name="configure-shared-parameters"></a>Konfigurowanie udostępnionych parametrów

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Należy skonfigurować wspólne parametry dla rekordów współużytkowanych przez wiele firm, takie jak rekordy **stanowisk**. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm.

Niektórych typy rekordów, np. **Stanowisko**, są współużytkowane w wielu firmach. Dla tych rekordów należy skonfigurować wspólne parametry. Na przykład na stronie **Udostępniane parametry Human resources** można ustawić parametry modułu Zasoby ludzkie dla różnych firm. 

Na stronie **Udostępniane parametry zasobów ludzkich** parametry są pogrupowane według obszarów na podstawie ich funkcji. 

### <a name="settings"></a>Ustawienia
Na karcie **Identyfikacja** trzeba wybrać typy identyfikacji, które reprezentują numery identyfikacyjne, które znajdują się na stronie. Identyfikację typów należy skonfigurować przed rozpoczęciem wprowadzania informacji identyfikacyjnych dla pracowników. Informacje o numerze PESEL, numerze dowodu osobistego, numerze obcego dowodu osobistego i osobistym kodzie identyfikacyjnym są obsługiwane na stronie **Typ identyfikacji**. Aby zdefiniować nowy typ identyfikacji lub sprawdzić listę istniejących typów, kliknij kolejno opcje **Zarządzanie pracownikami** &gt; **karta Linki** &gt; **Ustawienia** &gt; **Typy identyfikacji**. Można wprowadzić prosty kod i opis. 

Na karcie **Sekwencje identyfikatorów** można wybrać kolejne numery używane dla następujących rekordów: **numer pracownika**, **stanowisko**, **identyfikator zgłoszenia użytkownika**, **dokumentu I-9**, **kandydat**, **dyskusja**, **identyfikator świadczenia** i **akcja dotycząca pracowników** (jeśli ten typ rekordu jest włączony). Do obsługi odwołań do sekwencji identyfikatorów i kodów służy strona listy **Sekwencje identyfikatorów**. Aby znaleźć tę stronę, użyj funkcji wyszukiwania stron. 

Na karcie **Stanowiska** określ, czy są dostępne nowe stanowiska do domyślnego przypisania:

- **Zawsze** — Można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. Podczas tworzenia stanowisk data i godzina w obszarze **Dostępne do przypisania** na karcie **Ogólne** na stronie **Stanowisko** są automatycznie ustawiane na datę i godzinę utworzenia.
- **Nigdy** — nie można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. W przypadku wybrania tej opcji należy otworzyć stronę **Stanowisko** dla każdego nowego stanowiska, gdy będzie ono dostępne. Następnie, na karcie **Ogólne**, wprowadź datę **dostępnego przypisania**, aby włączyć przypisanie pracownika.

Na karcie **Dostęp zaawansowany** można ograniczyć dostęp do niektórych informacji lub łączy:

- **Ograniczenie dostępu do informacji o pracowniku** — Włącz tę funkcję, jeśli użytkownicy powinni mieć możliwość wyświetlania informacji o pracownikach tylko tych podmiotów prawnych, do których mają dostęp, oraz pracowników zatrudnionych w tych podmiotach prawnych.

    Po wybraniu tej funkcji wykonaj następujące kroki, aby ustawić odpowiednie uprawnienia dla każdego użytkownika, którego widok musi być ograniczony:

    1. Na stronie **Użytkownicy** wybierz użytkownika.
    1. Umożliwia wybór roli użytkownika. Opcja **Przypisz organizacje** staje się dostępna.
    1. Wybierz **Przypisz organizacje**.
    1. Na nowej stronie wybierz **Przyznaj dostęp indywidualnie określonym organizacjom**, a następnie wybierz organizacje, do których użytkownik powinien mieć dostęp.
    1. Powtórz kroki od 2 do 4 dla każdej innej roli użytkownika, w tym dla roli użytkownika systemu.

    > [!NOTE]
    > Firmy, do których użytkownik ma dostęp, muszą się dopasować do wszystkich ról użytkownika.

- **Włącz widok wynagrodzeń między firmami** — wynagrodzenie dla pracowników jest przypisywane do firmy zatrudnienia. Czasami pracownik może być zatrudniony jednocześnie w wielu podmiotach prawnych. Gdy ta funkcja jest włączona, wynagrodzenie dla każdego podmiotu prawnego będzie wyświetlane w **Samoobsługi pracowników** i **samoobsługi menedżera** bez konieczności zmiany podmiotów prawnych. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
