---
title: Organizowanie składników raportu w projektancie raportów
description: W tym temacie wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d348993422b24776098657dcef25a088ba2f826b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564550"
---
# <a name="organize-report-components-in-report-designer"></a>Organizowanie składników raportu w projektancie raportów

[!include [banner](../includes/banner.md)]

Po zaprojektowaniu bloków konstrukcyjnych i wygenerowaniu raportów przydatne jest zorganizowania tych obiektów, tak aby użytkownicy mogli je łatwiej znaleźć. W tym artykule wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów.

Można zmieniać nazwy folderów, raportów, bloków konstrukcyjnych i innych obiektów w projektancie raportów, aby ułatwić organizowanie plików. W zależności od typu obiektu, którego nazwa jest zmieniana, może być konieczna aktualizacja skojarzeń z tym obiektem.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Zmienianie nazwy folderu lub bloku konstrukcyjnego w Projektancie raportów
W Projektancie raportów można zmieniać nazwy folderów, definicji raportów, definicji wierszy, definicji kolumn i definicji drzew raportowania.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Zmienianie nazwy folderu lub modułu konstrukcyjnego w Projektancie raportów

1. W Projektancie raportów użyj okienka nawigacji, aby zlokalizować folder lub obiekt, którego nazwę chcesz zmienić.
2. Kliknij prawym przyciskiem myszy folder lub obiekt, a następnie kliknij przycisk **Zmień nazwę**. Pole **Nazwa** w okienku nawigacji staje się dostępne.
3. Wpisz nową nazwę, a następnie naciśnij klawisz Enter.
4. Jeśli blok konstrukcyjny jest definicją wiersza, kolumny lub drzewa raportowania, należy zaktualizować pozostałe skojarzone z nim bloki konstrukcyjne. Kliknij prawym przyciskiem myszy blok konstrukcyjny, którego nazwa została zmieniona w kroku 3, wybierz opcję **Skojarzenia**, a następnie wybierz pozycję na liście, aby ją zaktualizować.
5. Powtórz krok 4, dopóki nie zostaną zaktualizowane wszystkie powiązane elementy.

## <a name="create-and-manage-report-groups"></a>Umożliwia tworzenie grup raportów i zarządzanie nimi.
Można grupować definicje raportów, by generować wiele raportów w tym samym czasie. Do tworzenia, modyfikowania, usuwania i generowania grup raportów wymagana jest rola projektanta lub administratora. Użytkownicy z rolą generatora mogą tworzyć grupy raportów, a także modyfikować ustawienie dotyczące definicji raportów użytkownika dla grup raportów.

### <a name="create-a-report-group"></a>Tworzenie grupy raportów

1. W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2. W menu **Plik** kliknij kolejno opcje **Nowy** &gt; **Definicja grupy raportów**, aby otworzyć nową grupę raportów w oknie podglądu. Alternatywnie kliknij przycisk **Grupa raportów** ![Grupa raportów](media/report-group.gif "Grupa raportów") na pasku narzędzi.
3. Kliknij kartę **Grupa raportów**. Aby zastąpić informacje o definicjach poszczególnych raportów do generowania tego raportu, zaznacz pole wyboru **Zastąp ustawienia firmy, szczegółów i daty z poszczególnych definicji raportów**. Nazwa firmy, poziom szczegółowości, ustawienie tymczasowości i informacje o datach są wypełniane automatycznie, ale można je aktualizować.
4. Aby wygenerować wiele raportów z walutami raportowania, zaznacz pole wyboru **Uwzględnij wszystkie waluty raportowania**. Następnie podczas oglądania raportów w przeglądarce sieci web można kliknąć przycisk **Waluta**, a będzie dostępnych wiele widoków.
5. W polu **Raporty w grupie** kliknij opcję **Dodaj**, aby wybrać raporty w celu ich dodania do grupy raportów. Aby wybrać wiele raportów w oknie dialogowym **Dodaj**, przytrzymaj klawisz Ctrl podczas wybierania raportów. Po zakończeniu wybierania raportów kliknij przycisk **OK**.
6. Kliknij kolejno opcje **Plik** &gt; **Zapisz**, aby zapisać nową grupę raportów.

### <a name="modify-a-report-group"></a>Modyfikowanie grupy raportów

1. W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2. Kliknij dwukrotnie grupę raportów, którą chcesz zmodyfikować.
3. Na karcie **Grupa raportów** wprowadź żądane zmiany.
4. W menu **Plik** kliknij polecenie **Zapisz**, aby zapisać zmodyfikowaną grupę raportów. Alternatywnie kliknij przycisk **Zapisz** ![Zapisz](media/save.gif "Zapisz") na pasku narzędzi.

> Jeśli masz zaplanowane raporty do generowania w ustalonych odstępach czasu, można zastąpić te ustawienia i natychmiast wygenerować raport.

### <a name="generate-a-report-group-report"></a>Generowanie raportu grupy raportów

1. W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2. Otwórz grupę raportów do wygenerowania.
3. Kliknij przycisk **Generuj raport** ![Generuj raport](media/generate-report.gif "Generuj raport"), aby wygenerować raport.

### <a name="delete-a-report-group"></a>Usuwanie grupy raportu

1. W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2. Kliknij prawym przyciskiem myszy grupę raportów, którą chcesz usunąć, i wybierz polecenie **Usuń**.
3. Gdy pojawi się komunikat potwierdzający, kliknij przycisk **Tak**.

## <a name="report-group-tab-controls"></a>Formanty karty Grupa raportów
W poniższej tabeli opisano formanty istniejące na karcie **Grupa raportów**.

<table>
<thead>
<tr>
<th>Kontrola</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Zastępowanie firmy, szczegółów i ustawień danych z indywidualnych definicji raportów</td>
<td>Zaznaczenie tego pola wyboru umożliwia zastąpienie indywidualnych definicji raportów w danej grupie raportów tylko pod kątem generowania tych raportów.</td>
</tr>
<tr>
<td>Nazwa firmy</td>
<td>Wybierz firmę do użytku w tych raportach.</td>
</tr>
<tr>
<td>Poziom podsumowania</td>
<td>Określ poziom szczegółowości raportów.
<ul>
<li><strong>Finanse</strong> — Raport sumaryczny wysokiego poziomu. Nie można wyświetlić szczegółów kont i wymiarów, z wyjątkiem tych, które zostały dodane przy użyciu drzewa raportowania.</li>
<li><strong>Finanse i konto</strong> — raport zawierający ogólne podsumowanie i szczegóły konta.</li>
<li><strong>Finanse, konto i transakcja</strong> — raport zawierający ogólne podsumowanie i szczegóły transakcji.</li>
</ul></td>
</tr>
<tr>
<td>Tymczasowe</td>
<td>Określ typy działań objętych raportami.
<ul>
<li><strong>Tylko zaksięgowane działania</strong> — Raport będzie zawierał tylko transakcje i salda zaksięgowane w danych finansowych.</li>
<li><strong>Zaksięgowane i niezaksięgowane działania</strong> — Raport będzie zawierał wszystkie transakcje i salda wprowadzone oraz zaksięgowane w danych finansowych.</li>
<li><strong>Tylko niezaksięgowane działania</strong> — Raport będzie zawierał tylko transakcje, które zostały wprowadzone do danych finansowych, ale nie są jeszcze zaksięgowane.</li>
</ul></td>
</tr>
<tr>
<td>Uwzględnij wszystkie waluty raportowania</td>
<td>W tym miejscu są wyświetlone wszelkie dodatkowe waluty raportowania skonfigurowane w systemie Microsoft Dynamics ERP. Zaznacz to pole wyboru, aby generować dodatkowe raporty we wskazanych walutach. Aby wyświetlić te raporty w Podglądzie sieci Web, kliknij przycisk <strong>Waluta</strong> i wybierz walutę.</td>
</tr>
<tr>
<td>Informacje o dacie niezapisane w definicji raportu</td>
<td><ul>
<li>Okres podstawowy</li>
<li>Rok podstawowy</li>
<li>Objęty okres</li>
</ul>
W definicji raportu są zapisywane tylko ustawienia domyślnego okresu podstawowego.</td>
</tr>
<tr>
<td>Informacje o dacie nie są zapisane w definicji raportu</td>
<td><ul>
<li>Data raportu</li>
<li>Domyślny okres podstawowy</li>
</ul></td>
</tr>
<tr>
<td>Raporty w grupie</td>
<td>Dodawanie, usuwanie i zmienianie kolejności raportów w grupie raportów.
<ul>
<li>Aby dodać definicje raportów do grupy raportów, kliknij dwukrotnie grupę raportów, aby ją otworzyć, a następnie kliknij przycisk <strong>Dodaj</strong>. Zaznacz raporty, które chcesz umieścić w grupie raportów, a następnie kliknij przycisk <strong>OK</strong>.</li>
<li>Aby usunąć raport z grupy raportów, zaznacz go, a następnie kliknij przycisk <strong>Usuń</strong>.</li>
<li>Aby zmodyfikować kolejność, w jakiej raporty są generowane, wybierz raport na liście, a następnie kliknij przycisk <strong>Przenieś w górę</strong> lub <strong>Przenieś w dół</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Dodatkowe zasoby

[Raportowanie finansowe](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]