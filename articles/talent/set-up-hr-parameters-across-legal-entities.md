---
title: "Konfigurowanie parametrów modułu Zasoby ludzkie w wielu firmach"
description: "Należy skonfigurować wspólne parametry dla rekordów współużytkowanych przez wiele firm, takie jak rekordy stanowisk. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: cc5acf7ba1b350ee2c91923c7de3b4780385f3ef
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---

# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a>Konfigurowanie parametrów modułu Zasoby ludzkie w wielu firmach

[!include [banner](includes/banner.md)]

Należy skonfigurować wspólne parametry dla rekordów współużytkowanych przez wiele firm, takie jak rekordy stanowisk. W tym artykule wyjaśniono, jak skonfigurować parametry modułu Zasoby ludzkie dla różnych firm.

Niektórych typy rekordów, np. Stanowisko, są współużytkowane w wielu firmach. Dla tych rekordów należy skonfigurować wspólne parametry. Na przykład na stronie **Udostępniane parametry zasobów ludzkich** można ustawić parametry modułu Zasoby ludzkie dla różnych firm. 

Na stronie **Udostępniane parametry zasobów ludzkich** parametry są pogrupowane według obszarów na podstawie ich funkcji. 

### <a name="previously-released-functionality"></a>Wcześniej wydane grupy funkcjonalności
Na karcie **Identyfikacja** trzeba wybrać typy identyfikacji, które reprezentują numery identyfikacyjne, które znajdują się na stronie. Identyfikację typów należy skonfigurować przed rozpoczęciem wprowadzania informacji identyfikacyjnych dla pracowników. Informacje o numerze PESEL, numerze dowodu osobistego, numerze obcego dowodu osobistego i osobistym kodzie identyfikacyjnym są obsługiwane na stronie **Typ identyfikacji**. Aby zdefiniować nowy typ identyfikacji lub sprawdzić listę istniejących typów, kliknij kolejno opcje **Zarządzanie pracownikami** &gt; **karta Linki** &gt; **Ustawienia** &gt; **Typy identyfikacji**. Można wprowadzić prosty kod i opis. 

### <a name="if-youre-using-dynamics-365-for-talent"></a>Jeśli używasz programu Dynamics 365 for Talent
Na karcie **Identyfikacja** trzeba wybrać typy identyfikacji, które reprezentują numery identyfikacyjne, które znajdują się na stronie. Identyfikację typów należy skonfigurować przed rozpoczęciem wprowadzania informacji identyfikacyjnych dla pracowników. Informacje o numerze PESEL, numerze dowodu osobistego, numerze obcego dowodu osobistego i osobistym kodzie identyfikacyjnym są obsługiwane na stronie **Typ identyfikacji**. Aby zdefiniować nowy typ identyfikacji lub sprawdzić listę istniejących typów, kliknij kolejno opcje **Zasoby ludzkie** &gt; **Ustawienia** &gt; **Typy identyfikacji**. Można wprowadzić prosty kod i opis. 

Na karcie **Sekwencje identyfikatorów** można wybrać kolejne numery używane dla następujących rekordów: numer pracownika, stanowisko, identyfikator zgłoszenia użytkownika, dokumentu I-9, kandydat, dyskusja, identyfikator świadczenia i akcja dotycząca pracowników (jeśli ten typ rekordu jest włączony). Do obsługi odwołań do sekwencji identyfikatorów i kodów służy strona listy **Sekwencje identyfikatorów**. Aby znaleźć tę stronę, użyj funkcji wyszukiwania stron. 

Na karcie **Stanowiska** określ, czy są dostępne nowe stanowiska do domyślnego przypisania:

-   **Zawsze** — Można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. Podczas tworzenia stanowisk data i godzina w obszarze **Dostępne do przypisania** na karcie **Ogólne** na stronie **Stanowisko** są automatycznie ustawiane na datę i godzinę utworzenia.
-   **Nigdy** — nie można przypisać pracowników do nowych stanowisk podczas tworzenia stanowisk. Jeśli zostanie wybrana ta opcja, należy otworzyć stronę **Stanowisko** dla każdego nowego stanowiska, gdy staje się dostępne, a następnie na karcie **Ogólne** wpisać datę **Dostępne do przypisania**, aby umożliwić przypisanie pracownika.


<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Konfigurowanie parametrów modułu zasobów ludzkich specyficznych dla firmy](set-up-company-specific-hr-parameters.md)




