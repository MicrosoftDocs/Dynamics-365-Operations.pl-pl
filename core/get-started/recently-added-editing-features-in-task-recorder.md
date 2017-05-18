---
title: "Ostatnio dodane funkcje edycji w rejestratorze zadań"
description: "Jeśli używasz rejestratora zadań do tworzenia przewodników po zadaniach, można sprawniej edytować pliki za pomocą funkcji opisanych w tym temacie."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3be54879494948f75b192fcc22239b9064173220
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Ostatnio dodane funkcje edycji w rejestratorze zadań

[!include[banner](../includes/banner.md)]


Jeśli używasz rejestratora zadań do tworzenia przewodników po zadaniach, można sprawniej edytować pliki za pomocą funkcji opisanych w tym temacie.

Te funkcje są dostępne w menu **Ustawienia &gt; Rejestrator zadań &gt; Edytuj nagranie**.

-   Wstawianie kroków bez konieczności ponownego nagrywania całego pliku.
-   Przenoszenie kroków w podzadaniu bez konieczności ponownego nagrywania całego pliku.
-   Zwijanie pól nazwy i opisu nagrania.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Wstawianie kroków bez ponownego nagrywania całego pliku
Teraz można dodać krok w dowolnym miejscu przewodnika po zadaniu bez konieczności odtwarzania ani ponownego nagrywania całego pliku.

1.  Zaznacz krok, po którym ma zostać wstawiony nowy krok. Upewnij się, że ten krok jest wyróżniony.

Aby rejestrator zadań wstawił krok, musi być otwarta odpowiednia strona. Odpowiednią stroną jest strona, na której odbywa się nowy krok. Rejestrator zadań zawiera mechanizm, który rozpoznaje, która strona jest aktywna, i wyłącza funkcję, jeśli nie jest otwarta odpowiednia strona. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Gdy jesteś na poprawnej stronie, opcja **Wstaw krok** staje się dostępna.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Kliknij przycisk **Wstaw krok**.

Po kliknięciu przycisku **Wstaw krok** Rejestrator zadań przełącza się do trybu nagrywania. Wszystkie czynności wykonywane w interfejsie użytkownika będą teraz rejestrowane i dodawane jako kroki.

3. Kliknij przycisk **Zatrzymaj**.

Proces można powtarzać, dodając dowolną liczbę kroków lub przenosząc dowolną liczbę podzadań (zobacz poniżej punkt o podzadaniach).

4. Po zakończeniu edycji przewodnika po zadaniu kliknij przycisk **Zakończono edycję**, a następnie wybierz jedną z opcji, aby zapisać lub opublikować przewodnik po zadaniu.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Przenoszenie kroków w podzadaniu bez konieczności ponownego nagrywania całego pliku
Kroki podzadania można przenosić bez konieczności odtwarzania ani ponownego nagrywania całego pliku. Kroki podzadań i podzadań końcowych można również przenosić i kończyć, jeśli chcesz zgrupować istniejący blok kroków.

1.  Zaznacz krok lub krok podzadania, który chcesz przenieść. Upewnij się, że ten krok jest wyróżniony.
2.  Kliknij przycisk wielokropka, a następnie kliknij przycisk **Przenieś krok za**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Zaznacz krok lub krok podzadania, za który chcesz przenieść wybrany krok lub krok podzadania. Rejestrator zadań przeniesie ten krok.

4. Aby przenieść krok podzadania lub podzadania końcowego, zaznacz go, kliknij przycisk wielokropka, kliknij przycisk **Przenieś krok za**, a następnie zaznacz krok, po którym chcesz umieścić krok podzadania końcowego.

Jeśli chcesz, aby pierwszy krok przewodnika po zadaniu znalazł się w podzadaniu, utwórz krok podzadania jako drugi krok, a następnie przesuń do niego pierwszy krok. Można dodawać i przenosić dowolną liczbę kroków i podzadań.

5. Po zakończeniu edycji przewodnika po zadaniu kliknij przycisk **Zakończono edycję**, a następnie wybierz jedną z opcji, aby zapisać lub opublikować przewodnik po zadaniu.

## <a name="collapse-recording-name-and-description"></a>Zwijanie pól nazwy i opisu nagrania
Pola **Nazwa nagrania** i **Opis nagrania** można rozwijać i zwijać. Kiedy te pola są zwinięte, będzie widać więcej kroków w okienku edycji w Rejestratorze zadań. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Skrócony wykaz funkcji Rejestratora zadań](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)




