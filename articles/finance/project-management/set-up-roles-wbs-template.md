---
title: Ustawianie ról w szablonach struktury podziału pracy
description: Ten temat zawiera informacje dotyczące ustawiania roli w szablonach struktury podziału pracy.
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
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760636"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Ustawianie ról w szablonach struktury podziału pracy

[!include [banner](../includes/banner.md)]

Kierownicy projektów mogą skonfigurować szablony struktury podziału pracy (WBS), które będą stosować podczas tworzenia WBS dla nowych projektów. Kierownicy projektów mogą dodawać role podczas tworzenia szablonów. Poniższa procedura umożliwia przypisanie roli do szablonu struktury podziału pracy.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** > **Ustawienia** > **Projekty** > **Szablony struktury podziału pracy**.
2. Wybierz przycisk **Szczegóły** obok wybranego szablonu struktury podziału pracy.
3. Wybierz zadanie na liście, a następnie w polu **Rola** wybierz rolę, którą chcesz przypisać do zadania.

## <a name="work-with-a-wbs"></a>Praca z SPP

Można utworzyć nową SPP albo skopiować SPP z istniejącego szablonu struktury podziału pracy. Kierownik projektu może łatwo zarządzać zasobami poprzez przypisywanie ról do nowych zadań w SPP. Role mogą być zastępowane po pozyskaniu zasobu lub po zidentyfikowaniu potwierdzonego zasobu do pracy nad zadaniem. Ta elastyczność umożliwia kierownikom projektów wykonywanie następujących zadań:

- Identyfikacja liczby zasobów wymaganych dla pakietów prac w SPP.
- Szacowanie kosztów projektów.
- Określanie budżetu wstępnego.
- Szacowanie czasu trwania działań na podstawie ról i zasobów.
- Opracowanie pewnych planów zarządzania projektami na podstawie dostępnych informacji o projektach.

W SPP zostały dodane nowe opcje pomagające lepiej wykorzystywać funkcje organizowania zasobów.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opcja</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Przypisania zasobów</td>
<td>Wyświetlanie przydzielonych zasobów, dat, liczby godzin i typu rezerwacji dla zadań w SPP.</td>
</tr>
<tr class="even">
<td>Automatycznie generuj zespół</td>
<td>Automatyczne dodawanie zaplanowanych zasobów przy użyciu ról skojarzonych z zadaniem. Finance automatycznie sugeruje zaplanowane zasoby na podstawie wyników wielowątkowej analizy decyzyjnej opartej na rolach. Po skonfigurowaniu ról i nakładu pracy (w godzinach) dla zadań w SPP i po zwolnieniu struktury wybierz przycisk <strong>Automatycznie generuj zespół</strong>. Wymagana liczba zaplanowanych zasobów zostanie dodana do SPP i karty <strong>Zespół projektu i planowanie</strong>.</td>
</tr>
<tr class="odd">
<td>Zasób (lista rozwijana)</td>
<td>Na stronie <strong>Uruchom formularz przypisania zasobu</strong> można wybrać zasoby do rezerwacji ostatecznych lub wstępnych na podstawie określonego czasu trwania. Można dostosować ustawienia widoku, aby zobaczyć i ustawić czas trwania działań zasobu. Można wybierać i przypisywać zasoby na poziomie pakietu prac za pomocą następujących opcji:
<ul>
<li><strong>Akceptuj</strong> — potwierdzenie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Anuluj</strong> — anulowanie modyfikacji zasobu przypisanego do zadania.</li>
<li><strong>Przypisz automatycznie</strong> — dostępny zasób pracownika mający pasującą rolę jest automatycznie wybierany i przypisywany do zaznaczonego zadania.</li>
</ul></td>
</tr>
</tbody>
</table>

1. Na stronie **Wszystkie projekty** wybierz projekt **Uaktualnianie XYZ faza 2**.
2. Wybierz kolejno opcje **Plan** > **Działania** > **Struktura podziału pracy**.
3. Wybierz przycisk **Nowy**, aby dodać następujące działania pierwszego poziomu do struktury podziału pracy:

    - Inicjowanie
    - Planowanie
    - W trakcie
    - Monitorowanie i kontrola
    - Zamykanie

4. Ustaw daty i nakład pracy (godziny), jak pokazano na poniższej ilustracji.

    [![Ustawianie dat i nakładu pracy](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Wybierz wiersz zadania **Inicjowanie**, a następnie w polu **Rola** wybierz opcję **Starszy kierownik projektu**.
6. Wybierz opcję **Publikuj**.
7. W tym samym wierszu w polu **Zasoby** zaznacz element **Daniel Goldschmidt**, a następnie wybierz opcję **Akceptuj**.
8. Wybierz wiersz zadania **Planowanie**, a następnie w polu **Rola** wybierz opcję **Analityk biznesowy**.
9. Wybierz kolejno opcje **Publikuj** i **Automatycznie generuj zespół**.
10. W wyświetlonym oknie wiadomości wybierz przycisk **Tak**.
11. W polu **Zasoby** sprawdź, czy wartość to **Analityk biznesowy 1**.
12. Dla zasobu **Analityk biznesowy 1** otwórz wyszukiwanie i wybierz przycisk **Uruchom przypisanie zasobów###**. Następnie wybierz pracownika dla zadania.
13. Wybierz kolejno opcje **Przypisz wstępnie** &gt; **Pełne zdolności produkcyjne**.

    > [!NOTE] 
    > Nie pojawi się ostrzeżenie, że określonym zasobem jest teraz 2, ponieważ liczba zasobów nadal wynosi 1.

14. Na stronie **Struktury podziału pracy** sprawdź poprawność przypisania zasobów w SPP, a następnie wybierz przycisk **Zapisz**.
