---
title: "Ostatnio dodane funkcje edycji w programie Rejestrator zadań"
description: "Jeśli program task recorder umożliwia tworzenie prowadnic zadań, można edytować pliki usprawniają funkcje opisane w tym wiki."
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
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Ostatnio dodane funkcje edycji w programie Rejestrator zadań

Jeśli program task recorder umożliwia tworzenie prowadnic zadań, można edytować pliki usprawniają funkcje opisane w tym wiki.

Te funkcje są dostępne na **ustawienia &gt;Rejestrator zadań &gt;zapisu Edit** menu.

-   Wstaw czynności bez ponownego nagrywania całego pliku.
-   Przenieś kroki w ramach zadania podrzędne bez ponownego nagrywania całego pliku.
-   Zwijanie pola Nazwa i opis zapisu.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Wstaw czynności bez ponownego nagrywania całego pliku
Krok można teraz dodać dowolne miejsce w podręczniku zadania, bez odtwarzania lub ponowne nagrywanie całego pliku.

1.  Wybierz etap, po którym ma nowy krok do wstawienia. Upewnij się, że ten krok jest wyróżniony.

Aby Rejestrator zadań, aby wstawić etap musi mieć odpowiednie strony, Otwórz. Poprawnej strony jest strona, w których odbywa się nowy krok. Program Task recorder ma mechanizm, który określa co aktywna strona jest i spowoduje wyłączenie funkcji, jeśli odpowiednie strony nie jest otwarty. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Gdy są na odpowiedniej stronie, **Wstaw etap** stają się dostępne.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Kliknij **Wstaw etap**.

Po kliknięciu przycisku **Wstaw etap**, Rejestrator zadań przełącza się w tryb rekordu. Wszelkie działania podjęte w interfejsie użytkownika będą teraz rejestrowane i dodać w miejscu jako kroki.

3. Kliknij **Stop**.

Proces można powtarzać, dodając dowolną liczbę kroków lub przenosząc tyle podzadań, stosownie do potrzeb (zobacz poniżej zadania podrzędne).

4. Po zakończeniu edycji przewodnika zadania, kliknij przycisk **Zakończ edytowanie**, a następnie wybierz jedną z opcji, aby zapisać lub opublikować przewodnik zadania.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Przenieś kroki opisane w temacie staje się podzadaniem bez ponownego nagrywania całego pliku
Działania w ramach zadań podrzędnych można przenosić bez odtwarzania lub ponowne nagrywanie całego pliku. Jeśli chcesz zgrupować istniejącego bloku kroków, można przenieść zadanie podrzędne krok lub end sub zadanie krok.

1.  Zaznacz krok lub podzadania krok, który chcesz przenieść. Upewnij się, że ten krok jest wyróżniony.
2.  Kliknij przycisk wielokropka, a następnie kliknij przycisk **ruch krok po**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Zaznacz krok lub podzadania krok, który ma zostać przeniesiony krok lub podzadania krok po. Program Task recorder przeniesie ten krok.

4. Aby przenieść end sub zadanie krok, zaznacz go, kliknij przycisk wielokropka, kliknij przycisk **ruch krok po**, a następnie zaznacz krok, po którym ma krok podzadania zakończenia, aby być.

Jeśli pierwszym krokiem jest przewodnik zadań w ramach zadania podrzędne, należy utworzyć krok podzadania jako drugi krok, a następnie przesuń pierwszy krok do niego. Można dodać lub przenieść dowolną liczbę kroków lub zadań podrzędnych w razie potrzeby.

5. Po zakończeniu edycji przewodnika zadania, kliknij przycisk **Zakończ edytowanie**, a następnie wybierz jedną z opcji, aby zapisać lub opublikować przewodnik zadania.

## <a name="collapse-recording-name-and-description"></a>Zwiń rejestrującego nazwę i opis
Można rozwijać i zwijać **rejestrującego nazwę** i **nagrywania opis** pól. Kiedy te pola są zwinięte, więcej czynności będą widoczne w Rejestrator zadań edycji okienka. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie dokumentacji lub szkolenia przy użyciu nagrań zadań](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Podręczny wykaz Rejestrator zadań](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


