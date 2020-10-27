---
title: Dodawanie istniejącego działania do wersji przepływu produkcji
description: Podczas tworzenia nowych wersji przepływów produkcji można dodać działania utworzone dla starszych wersji do nowej wersji.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f95958e57b1b1a93e43eb2cf02d2651ccb9587b6
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979763"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Dodawanie istniejącego działania do wersji przepływu produkcji

[!include [banner](../../includes/banner.md)]

Podczas tworzenia nowych wersji przepływów produkcji można dodać działania utworzone dla starszych wersji do nowej wersji. Ta procedura pokazuje, jak nowa wersja jest tworzona dla istniejącego przepływu produkcji, bez kopiowania działań. W następnym kroku istniejące działanie jest dodawane do nowej wersji. 

Zadanie wymaga przepływu produkcji z już utworzoną wersją i działaniami.


## <a name="create-a-new-production-flow-version"></a>Utwórz nową wersję przepływu produkcji
1. Wybierz kolejno opcje Kontrola produkcji > Ustawienia > Przepływ produkcji oszczędnej > Przepływy produkcji.
2. Na liście znajdź i zaznacz odpowiedni rekord.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij przycisk Edytuj.
5. Na liście oznacz wybrany wiersz.
6. W polu Data wygaśnięcia wprowadź datę i godzinę.
    * Należy zauważyć, że przed utworzeniem nowej wersji przepływu produkcji trzeba sprawdzić datę i godzinę ważności aktywnej wersji. Nowa wersja zostanie utworzona z obowiązującą datą rozpoczęcia, która łączy się z datą ważności wybranej wersji.  
7. Kliknij przycisk Dodaj.
8. W polu Kopiuj z wersji wybierz opcję Nie.
    * Wybierz opcję Nie, aby rozpocząć od pustej wersji, jeśli większość działań skopiowanej wersji zostanie zastąpiona nowymi działaniami. Niezmienione działania dodaj ręcznie do funkcji Dodawanie istniejących w formularzu działania.  
9. W polu Duplikuj reguły Kanban wybierz pozycję Nie.
    * Jeżeli działania nie zostaną skopiowane do nowej wersji, nie można skopiować reguł Kanban podczas tworzenia nowej wersji.   Zamiast tego później użyjesz funkcji Tworzenie zastępczej reguły Kanban w formularzu Reguła Kanban w celu zastąpienia reguł Kanban starej wersji przepływu produkcji regułami Kanban używającymi działań nowej wersji.  
10. Kliknij przycisk OK.
11. Na liście znajdź i zaznacz odpowiedni rekord.

## <a name="add-an-existing-activity"></a>Dodawanie istniejącego działania
1. Kliknij opcję Działania.
2. Kliknij przycisk Dodawanie istniejących, aby otworzyć rozwijane okno dialogowe.
    * Znajdź i zaznacz istniejące działanie, które ma zostać dodane do nowej wersji przepływu produkcji.  Należy zauważyć, że lista zawiera wszystkie działania, które zostały utworzone dla tego przepływu produkcji we wszystkich poprzednich wersjach przepływu.  
3. Wprowadź lub wybierz wartość w polu Działanie.
4. Kliknij przycisk OK.

