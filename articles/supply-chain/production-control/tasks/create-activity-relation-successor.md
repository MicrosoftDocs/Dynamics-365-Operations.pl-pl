--- 
title: "Tworzenie relacji działań — Zdarzenie następujące"
description: "Przepływ działań w przepływie produkcji oszczędnej jest udokumentowany za pomocą relacji między działaniami."
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 75a76252cc3cb6f3e7516309a7d9a6f2d1934ccd
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-activity-relation-successor"></a>Tworzenie relacji działań: Zdarzenie następujące

[!include [task guide banner](../../includes/task-guide-banner.md)]

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


