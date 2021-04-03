---
title: Tworzenie relacji działań — Zdarzenie następujące
description: Przepływ działań w przepływie produkcji oszczędnej jest udokumentowany za pomocą relacji między działaniami.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5f10ecb8e579975327440ede6ea383226645c8cf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255308"
---
# <a name="create-activity-relation---successor"></a>Tworzenie relacji działań — Zdarzenie następujące

[!include [banner](../../includes/banner.md)]

Przepływ działań w przepływie produkcji oszczędnej jest udokumentowany za pomocą relacji między działaniami. W tym nagraniu pokazano, jak utworzyć relację między działaniami.

Wymagania wstępne:

- Przepływ produkcji i wersja robocza. 

- Dwa działania następujące po sobie w procesie produkcji są utworzone, ale nie powiązane.


## <a name="find-the-production-flow-version"></a>Znajdowanie wersji przepływu produkcji 
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Na liście oznacz wybrany wiersz.
5. Na liście zaznacz wersję roboczą.
    * Relacje między działaniami można dodawać do wersji roboczej i aktywnych przepływu produkcji.  

## <a name="open-the-activity-overview"></a>Otwieranie przeglądu działań
1. Kliknij opcję Działania.
    * Należy zwrócić uwagę, że w formularzu są wyświetlane wszystkie działania przepływu produkcji przydzielone do wersji przepływów produkcji, z którymi pracujesz.  

## <a name="add-a-successor"></a>Dodawanie zdarzenia następującego
1. Kliknij opcję Dodaj zdarzenie następujące.
2. W polu Działanie kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
3. Na liście znajdź i zaznacz odpowiedni rekord.
4. Na liście kliknij łącze w wybranym wierszu.
5. Zaznacz pole wyboru Ograniczenie.
6. W polu Wartość ograniczenia wprowadź liczbę.
    * Czas ograniczenia to czas, jaki należy zaplanować między zaplanowanym zakończeniem działania poprzedzającego (wymagana data i godzina) a zaplanowanym rozpoczęciem działania następującego.  
7. W polu Jednostki wpisz wartość.
8. W polu Wskaźnik czasu cyklu wpisz liczbę.
    * Jeśli oba działania są wykonywane z tym samym taktem, współczynnik czasu cyklu powinien wynosić 1. Jeśli zdarzenie poprzedzające odbywa się dwa razy szybciej niż działanie następujące, współczynnik powinien wynosić 2.   Współczynniki czasu cyklu są używane do obliczania poszczególnych czasów cyklu dla działań przepływu produkcji.  
9. Kliknij przycisk OK.
10. Zamknij stronę.
11. Kliknij kartę GridPanel.
12. Zamknij stronę.
13. Odśwież stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]