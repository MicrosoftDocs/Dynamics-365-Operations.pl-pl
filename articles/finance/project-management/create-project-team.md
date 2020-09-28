---
title: Tworzenie zespołu projektu
description: Ten temat zawiera informacje o metodach tworzenia zespołów projektu i zarzadzania nimi.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834a6c0a4fcc32a955c1feddf0a6cbbb1f16b869
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760634"
---
# <a name="create-a-project-team"></a>Tworzenie zespołu projektu

[!include [banner](../includes/banner.md)]

Aby korzystać z ról, które zostały wcześniej skonfigurowane w projekcie, kierownik projektu musi skojarzyć role z projektem. Do projektu można przypisać wiele ról. Aby uniknąć nieporozumień, te role są automatycznie znakowane podczas rezerwowania. Na przykład jeśli kierownik projektu potrzebuje trzech inżynierów oprogramowania, następuje automatyczne wygenerowanie trzech ról inżyniera oprogramowania z etykietami **Inżynier oprogramowania 1**, **Inżynier oprogramowania 2** i **Inżynier oprogramowania 3**. Jeśli wcześniej skonfigurowano cechy roli, są one stosowane jako filtr podczas wyszukiwania zasobu. W razie potrzeby mogą być dodawane dodatkowe charakterystyki, aby bardziej zawęzić wyszukiwanie.

Można również dostosować ustawienia widoku, aby lepiej widzieć dostępność zasobów. Istnieją opcje pokazywania dostępności w ujęciu godzinowym, dziennym, tygodniowym, miesięcznym, kwartalnym i rocznym. Dostępna jest także opcja pokazywania dostępnych i pozostałych zdolności produkcyjnych zasobów. Ta opcja jest przydatna dla zarządzania czasem podczas szacowania czasu dostępnego na działania lub czasu dostępności zasobów.

Kierownik projektu może wybrać rolę na stronie, a następnie — jeśli jest dostępny zasób spełniający zapotrzebowanie — zarezerwować zasób w celu wypełnienia roli. Należy zwrócić uwagę, że zasoby nie muszą być rezerwowane w tym momencie na etapie planowania. Podczas tworzenia SPP można zastąpić role zasobami pracowników dla projektu. Jeśli role zostaną zastąpione zasobami pracowników w SPP, konfiguracja zasobów automatycznie aktualizuje schemat i harmonogram zespołu projektu.

[![Schemat zespołu projektu zawierający role i rzeczywiste zasoby](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

Kierownik projektu ma różne opcje rezerwowania zasobu dla projektu, takie jak **Pozostałe zdolności produkcyjne**, **Pełne zdolności produkcyjne**, **Procent zdolności produkcyjnych** i **Określ godziny**. Te opcje rezerwacji można anulować w dowolnym momencie w razie zmiany przydziałów zasobów. Obsługiwane są dwa rodzaje rezerwacji:

- **Rezerwacje ostateczne** — rezerwacja zasobu została zatwierdzona i potwierdzona do pracy nad projektem przez określony czas.
- **Rezerwacje wstępne** — rezerwacja zasobu została wstępnie ustawiona do pracy nad projektem przez określony czas.

Poniżej znajduje się procedura wyjaśniająca tworzenie zespołu projektu.

## <a name="create-a-project-team"></a>Tworzenie zespołu projektu

1. Na stronie listy **Wszystkie projekty** zaznacz projekt, a następnie wybierz przycisk **Edytuj**.
2. Na karcie **Zespół projektu i planowanie** w polu **Zaplanuj datę rozpoczęcia** wprowadź datę rozpoczęcia harmonogramu plus jeden miesiąc. Na przykład jeśli datą początkową harmonogramu jest 24 czerwca 2017 r. (24.06.2017), wprowadź **24.07.2017**.
3. Wybierz opcję **Dodaj**.
4. W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Starszy kierownik projektu**.
5. Wybierz opcję **Wymagane kompetencje**.
6. Na stronie **Wybierz charakterystyki** są domyślnie zaznaczone cechy, które zostały wcześniej ustawione dla roli Starszy kierownik projektu. Kliknij przycisk **OK**.
7. Na stronie **Dodaj role do projektu** w polu **Liczba zasobów** wprowadź **1**.
8. W polu **Zasób** w wynikach wyszukiwania będą widoczne wszystkie zasoby posiadające wymagane kompetencje. Zaznacz pozycję **Daniel Goldschmidt**, a następnie wybierz przycisk **Utwórz**.
9. Na stronie **Projekt** wybierz przycisk **Dodaj**.
10. W okienku **Dodaj role do projektu** w polu **Role** wybierz opcję **Członek zespołu**. W polu **Liczba zasobów** wpisz **5**.
11. Wybierz opcję **Utwórz**.
12. Na stronie **Projekty** wybierz opcję **Wykorzystaj zasób**.

## <a name="monitor-project-teams"></a>Monitorowanie zespołów projektu
1. Na stronie **Wszystkie projekty** wybierz łącze **Identyfikator projektu** dla projektu **Uaktualnianie XYZ faza 2**.
2. Na skróconej karcie **Zespół projektu i planowanie** sprawdź poprawność wyświetlanych zasobów projektu.
