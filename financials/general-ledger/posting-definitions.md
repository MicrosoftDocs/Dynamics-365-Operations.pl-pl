---
title: "Definicje księgowania"
description: "Ten artykuł zawiera informacje o definicjach księgowania oraz o sposobach ich tworzenia i łączenia. Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 357ae498e84ef27e46142c7dcc0f90ecb0ee9f1c
ms.lasthandoff: 03/31/2017


---

# <a name="posting-definitions"></a>Definicje księgowania

Ten artykuł zawiera informacje o definicjach księgowania oraz o sposobach ich tworzenia i łączenia. Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych.

Dla obsługiwanych typów księgowania i dokumentów można używać definicji księgowania zamiast profili księgowania do klasyfikacji kont głównych i wymiarów finansowych dla zapisów księgowych. Obsługiwane dokumenty i typy księgowania można wyświetlić na stronie **Definicje księgowania transakcji**. 

Aby rozpocząć korzystanie z definicji księgowania, należy wybrać opcję **Użyj definicji księgowania** na stronie **Parametry księgi głównej**. Nawet jeśli korzystasz z definicji księgowania, nadal musisz zdefiniować profile księgowania dla inicjowanych wpisów i nieobsługiwanych typów księgowania i dokumentów. 

Definicje księgowania są wymagane do obsługi księgowania przyszłych zobowiązań wiążących dla zamówień zakupu i oraz przyszłych zobowiązań niewiążących dla zapotrzebowań na zakup.

## <a name="defining-posting-definitions"></a>Określanie definicji księgowania
Użyj strony **Definicje księgowania**, aby określić kryteria uzgadniania i zdefiniować wpisy, które mają być generowane po wystąpieniu uzgodnienia. Kryteria uzgadniania są obliczane dla inicjowanych wpisów jako zasady podziału księgowań. 

Na stronie **Definicje księgowania** możesz też przypisać numery priorytetów do wierszy wpisu, aby ustalić kolejność oceniania wierszy. Wiersze z najniższym priorytetem są oceniany jako pierwsze. Na przykład oceniane są wszystkie wiersze z priorytetem 1, następnie wiersze z priorytetem 2 itd. Jeśli zostanie znaleziony odpowiednik, kryteria dopasowania są ignorowane. Oprócz tego tylko kryteria w grupie spełniających pierwotnej transakcji spowodować wpisu wygenerowanego 

Można sprawdzić poprawność definicji księgowania za pomocą kreatora **Testu definicji księgowania**. Po zdefiniowaniu wpisu, z którego pochodzi próbka do definicji księgowania, pojawią się wygenerowane wpisy. 

Możesz używać wersji definicji księgowania razem z datami obowiązywania. Na przykład możesz utworzyć przyszłą wersji definicji księgowania do księgowania na innym koncie księgowym w nowym roku obrachunkowym. 

Użyj strony **Definicje księgowania transakcji**, aby przypisać definicje księgowania do typów transakcji.

## <a name="linking-posting-definitions"></a>Łączenie definicji księgowania
Można tworzyć połączenia między definicjami księgowania podczas tworzenia nowej definicji księgowania. Kryteria definicji, z którą tworzone jest połączenie, są następnie uwzględniane oprócz kryteriów bieżącej definicji księgowania. Ta funkcja pomaga zaoszczędzić czas, ponieważ nie trzeba ponownie wprowadzić kryteriów na skróconej karcie **Wpisy** na stronie **Definicje księgowania** dla bieżącej definicji księgowania, jeśli te wiersze zostały już wpisane w innej definicji. 

Na wykresach lub w tabelach możesz uwzględnić dowolne łącza, których można użyć. Aby uniknąć konfliktów z bieżącą definicją księgowania, upewnij się, że wiersze we wszystkich definicjach księgowania, z którym tworzone jest połączenie, są niepowtarzalne. 

Przy tworzeniu połączeń w definicjach księgowania obowiązują następujące ograniczenia:

-   Definicja księgowania może łączyć się z inną definicją księgowania lub być połączona z inną definicją księgowania, ale nie może spełniać obu tych warunków jednocześnie. Definicja księgowania może być połączona z wieloma innymi definicjami księgowania.
-   Można konfigurować łącza tylko między definicjami księgowania znajdującymi się w tym samym module.
-   Definicję księgowania można przypisać do dowolnego typu transakcji, ale typ transakcji musi znajdować się w tym samym module co definicja księgowania. Użyj strony **Definicje księgowania transakcji**, aby zobaczyć, w jakim modelu jest typ transakcji.


Aby uzyskać więcej informacji, zobacz [Przykłady definicji księgowania](/general-ledger/example-posting-definitions.md). 

