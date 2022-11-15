---
title: Ustawianie zadań w Zarządzaniu zadaniami
description: W tym artykule wyjaśniono, jak skonfigurować zadania w Zarządzanie zadaniami w Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6a38cc2e36c24ddbfe0d8b2886301c108599ab25
ms.sourcegitcommit: 55e440e30490b2d36d86b22aa1263d5da97633aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2022
ms.locfileid: "9745392"
---
# <a name="set-up-tasks-in-task-management"></a>Ustawianie zadań w Zarządzaniu zadaniami

[!INCLUDE [PEAP](../includes/peap-1.md)]

W wersjach rozwiązania Microsoft Dynamics 365 Human Resources przed wersjami 10.0.30 użytkownicy, którzy chcą edytować zadanie, muszą pojedynczo edytować to zadanie na każdej liście kontrolnej, która go zawierała. Jednak w wersji 10.0.30 programu Zasoby ludzkie użytkownicy mogą wybierać sposób obsługi edytowanych zadań. Jeśli edytowane zadanie znajduje się na liście kontrolnej, należy wybrać opcję **Włącz aktualizację zarządzania zadaniami** na karcie **Zarządzanie zadaniami** na stronie **Parametry współużytkowane zasobów ludzkich**, aby włączyć listę kontrolną, aby użyć edytowanego zadania.

[![Włącz opcję uaktualnienia zarządzania zadaniami na stronie Udostępniane parametry zasobów ludzkich.](./media/task-update.png)](./media/task-update.png)

Jeśli edycja zadań powinna być stosowana do wszystkich skojarzonych zadań z listy kontrolnej, musi istnieć relacja między zadaniem w bibliotece zadań a zadaniem na liście kontrolnej. Dodano opcję, aby utworzyć relację między zadaniem biblioteki a zadaniem z listy kontrolnej.

Możesz tworzyć zadania pojedynczo, a następnie wykorzystywać je w wielu listach kontrolnych. Aby utworzyć zadanie, na stronie **Ustawienia onboardingu**, w zakładce **Zadania** wybierz **Nowe**.

## <a name="set-up-tasks"></a>Ustaw zadania

Aby przypisać utworzone zadanie do wielu list kontrolnych, wybierz zadanie, a następnie wybierz z menu opcję **Zastosuj do list kontrolnych** w menu.

Alternatywnie możesz dodawać zadania bezpośrednio do listy kontrolnej. Aby dodać zadanie do listy kontrolnej, na stronie **Konfiguracja onboardingu**, w zakładce **Lista kontrolna**, albo stwórz nową listę kontrolną, do której dodasz zadanie, albo dodaj zadanie do istniejącej listy kontrolnej.

Aby edytować zadanie w bibliotece, wybierz polecenie **Edytuj** w menu Biblioteka zadań. Jeśli zadanie jest skojarzone z listami kontrolnymi, zostaną one wyświetlone na stronie **Edytuj zadanie**. Jeśli chcesz, aby zadania z dowolnej listy kontrolnej były aktualizowane przy użyciu edycji, wybierz te listy kontrolne w sekcji **Zastosuj do list kontrolnych**.

Aby usunąć zadania z biblioteki, wybierz **Usuń**. Jeśli zadanie jest skojarzone z listą kontrolną, ta akcja nie spowoduje usunięcia zadania z tej listy kontrolnej. Do usunięcia zadania z listy kontrolnej jest wymagana osobna akcja.

### <a name="set-up-checklists"></a>Tworzenie list kontrolnych

Lista kontrolna to grupa zadań. Możesz stworzyć tyle list kontrolnych, ile potrzebujesz, i możesz przypisać te same zadania do wielu list kontrolnych. Kiedy tworzysz listę kontrolną, określasz jej właściciela i kalendarz.

Aby utworzyć nowe zadanie na liście kontrolnej, wybierz **Nowy** na pasku menu zadania. Podczas tworzenia nowego zadania można opcjonalnie dodać zadanie do biblioteki zadań, aby można je było udostępnić na wielu listach kontrolnych. Aby dodać zadanie do biblioteki zadań, należy ustawić opcję **Zastosuj zadanie do biblioteki** na **Tak**. W przypadku dodania zadania do biblioteki zadań można je jednocześnie dodać do innych list kontrolnych, wybierając te listy kontrolne w sekcji **Zastosuj do list kontrolnych**. Jeśli zdecydujesz się nie dodawać zadania do biblioteki zadań, zadanie będzie istnieć tylko na liście kontrolnej, na której je utworzysz.

Aby edytować zadanie na liście kontrolnej, wybierz opcję **Edytuj** w menu zadań. Jeśli zadanie jest skojarzone z listami kontrolnymi, zostaną one wyświetlone na stronie **Edytuj zadanie**. Jeśli chcesz, aby zadania z dowolnej innej listy kontrolnej były aktualizowane przy użyciu edycji, wybierz te listy kontrolne w sekcji **Zastosuj do list kontrolnych**.

Aby usunąć zadania z listy kontrolnej, wybierz pozycję **Usuń**. Ta akcja usuwa zadania tylko z listy kontrolnej. Nie spowoduje to jednak usunięcia zadań z biblioteki zadań. Aby usunąć zadania z biblioteki zadań, otwórz stronę **Biblioteka zadań** i wybierz **Usuń**.
