---
title: "Organizowanie składników raportu w projektancie raportów"
description: "Po zaprojektowaniu bloków konstrukcyjnych i wygenerowaniu raportów przydatne jest zorganizowania tych obiektów, tak aby użytkownicy mogli je łatwiej znaleźć. W tym artykule wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów."
author: RobinARH
manager: AnnBe
ms.date: 2016-03-07 19 - 06 - 25
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: Management Reporter, Core
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 
ms.dyn365.ops.version: 
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: c8efd57805cd89eb8cdfabe81a60704bb4390194
ms.lasthandoff: 03/29/2017


---

# <a name="organize-report-components-in-report-designer"></a>Organizowanie składników raportu w projektancie raportów

Po zaprojektowaniu bloków konstrukcyjnych i wygenerowaniu raportów przydatne jest zorganizowania tych obiektów, tak aby użytkownicy mogli je łatwiej znaleźć. W tym artykule wyjaśniono, jak organizować istniejące raporty, bloki konstrukcyjne i obiekty w projektancie raportów.

Można zmieniać nazwy folderów, raportów, bloków konstrukcyjnych i innych obiektów w projektancie raportów, aby ułatwić organizowanie plików. W zależności od typu obiektu, którego nazwa jest zmieniana, może być konieczna aktualizacja skojarzeń z tym obiektem.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>Zmienianie nazwy folderu lub bloku konstrukcyjnego w Projektancie raportów
W Projektancie raportów można zmieniać nazwy folderów, definicje raportów, definicje wierszy, definicje kolumn i definicje drzewa raportowania. **Uwaga:** Po zmianie nazwy bloku konstrukcyjnego należy zaktualizować wszelkie definicje raportowania, które używają tego bloku. W przeciwnym razie nie można wygenerować nowego raportu.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>Zmienianie nazwy folderu lub bloku konstrukcyjnego w Projektancie raportów

1.  W Konstruktorze raportów użyj okienka nawigacji, by znaleźć folder lub obiekt, którego nazwę chcesz zmienić.
2.  Kliknij prawym przyciskiem myszy folder lub obiekt, a następnie kliknij przycisk **Zmień nazwę**. Pole **Nazwa** w okienku nawigacji staje się dostępne.
3.  Wpisz nową nazwę, a następnie naciśnij klawisz Enter.
4.  Jeśli blok konstrukcyjny jest definicją wiersza, kolumny lub drzewa raportowania, należy zaktualizować pozostałe skojarzone z nim bloki konstrukcyjne. Kliknij prawym przyciskiem myszy blok konstrukcyjny, którego nazwa została zmieniona w kroku 3, wybierz opcję **Skojarzenia**, a następnie wybierz pozycję na liście, aby ją zaktualizować.
5.  Powtórz krok 4, dopóki nie zostaną zaktualizowane wszystkie powiązane elementy.

## <a name="create-and-manage-report-groups"></a>Umożliwia tworzenie grup raportów i zarządzanie nimi.
Można grupować definicje raportów, by generować wiele raportów w tym samym czasie. Do tworzenia, modyfikowania, usuwania i generowania grup raportów wymagana jest rola projektanta lub administratora. Użytkownicy z rolą generatora mogą tworzyć grupy raportów, a także modyfikować ustawienie dotyczące definicji raportów użytkownika dla grup raportów.

### <a name="create-a-report-group"></a>Tworzenie grupy raportów

1.  W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2.  Na **pliku** menu, kliknij przycisk **nowy**&gt;**definicji raportu grupy** otworzyć nową grupę raport w oknie podglądu. Alternatywnie, kliknij przycisk **raport grupy** przycisk ![raport grupy](https://i-technet.sec.s-msft.com/dynimg/IC679515.gif "raport grupy") na pasku narzędzi.
3.  Kliknij kartę **Grupa raportów**. Aby zastąpić informacje o definicjach poszczególnych raportów do generowania tego raportu, zaznacz pole wyboru **Zastąp ustawienia firmy, szczegółów i daty z poszczególnych definicji raportów**. Nazwa firmy, poziom szczegółowości, ustawienie tymczasowości i informacje o datach są wypełniane automatycznie, ale można je aktualizować.
4.  Aby wygenerować wiele raportów z walutami raportowania, zaznacz pole wyboru **Uwzględnij wszystkie waluty raportowania**. Następnie podczas oglądania raportów w przeglądarce sieci web można kliknąć przycisk **Waluta**, a będzie dostępnych wiele widoków.
5.  W polu **Raporty w grupie** kliknij opcję **Dodaj**, aby wybrać raporty w celu ich dodania do grupy raportów. Aby wybrać wiele raportów w oknie dialogowym **Dodaj**, przytrzymaj klawisz Ctrl podczas wybierania raportów. Po zakończeniu wybierania raportów kliknij przycisk **OK**.
6.  Kliknij **pliku**&gt;**zapisać** Aby zapisać nową grupę raportu.

### <a name="modify-a-report-group"></a>Modyfikowanie grupy raportów

1.  W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2.  Kliknij dwukrotnie grupę raportów, którą chcesz zmodyfikować.
3.  Na karcie **Grupa raportów** wprowadź żądane zmiany.
4.  Na **pliku** menu, kliknij przycisk **zapisać** Aby zapisać grupę zmodyfikowanego raportu, można też kliknąć **zapisać** przycisk ![zapisać](https://i-technet.sec.s-msft.com/dynimg/IC679516.gif "zapisać") na pasku narzędzi.

**Uwaga:** Jeśli masz zaplanowane raporty do generowania w ustalonych odstępach czasu, można zastąpić te ustawienia i natychmiast wygenerować raport.

### <a name="generate-a-report-group-report"></a>Generowanie raportu grupy raportów

1.  W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2.  Otwórz grupę raportów do wygenerowania.
3.  Kliknij **Generuj raport** przycisk ![Generuj raport](https://i-technet.sec.s-msft.com/dynimg/IC679517.gif "Generuj raport") do generowania raportów.

### <a name="delete-a-report-group"></a>Usuwanie grupy raportu

1.  W Projektancie raportów w okienku nawigacji kliknij opcję **Grupy raportów**.
2.  Kliknij prawym przyciskiem myszy grupę raportów, którą chcesz usunąć, i wybierz polecenie **Usuń**.
3.  Gdy pojawi się komunikat potwierdzający, kliknij przycisk **Tak**.

## <a name="report-group-tab-controls"></a>Formanty karty Grupa raportów
W poniższej tabeli opisano formanty istniejące na karcie **Grupa raportów**.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Kontrola</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Zastępowanie firmy, szczegółów i ustawień danych z indywidualnych definicji raportów</td>
<td>Zaznaczenie tego pola wyboru umożliwia zastąpienie indywidualnych definicji raportów w danej grupie raportów tylko pod kątem generowania tych raportów.</td>
</tr>
<tr class="even">
<td>Nazwa firmy</td>
<td>Wybierz firmę do użytku w tych raportach.</td>
</tr>
<tr class="odd">
<td>Poziom podsumowania</td>
<td>Określ poziom szczegółowości raportów.
<ul>
<li><strong>Finanse</strong> — raport wysokiego poziomu. Nie można wyświetlić szczegółów kont i wymiarów, z wyjątkiem tych, które zostały dodane przy użyciu drzewa raportowania.</li>
<li><strong>Finansowe &amp;konta</strong> − A raport, który zawiera podsumowanie wysokiego poziomu i szczegóły konta.</li>
<li><strong>Finansowe, konto, &amp;transakcji</strong> − A raport, który zawiera podsumowanie wysokiego poziomu i szczegóły transakcji.</li>
</ul></td>
</tr>
<tr class="even">
<td>Tymczasowe</td>
<td>Określ typy działań objętych raportami.
<ul>
<li><strong>Tylko zaksięgowane działania</strong> — obejmują tylko transakcje i salda, które są zaksięgowane w danych finansowych.</li>
<li><strong>Działania zaksięgowane i niezaksięgowane</strong> — obejmują wszystkie transakcje i salda, które zostały wprowadzone i zaksięgowane w danych finansowych.</li>
<li><strong>Tylko niezaksięgowane działania</strong> — obejmują tylko transakcje i salda, które zostały wprowadzone, ale nie są jeszcze zaksięgowane w danych finansowych.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Uwzględnij wszystkie waluty raportowania</td>
<td>W tym miejscu są wyświetlone wszelkie dodatkowe waluty raportowania skonfigurowane w systemie Microsoft Dynamics ERP. Zaznacz to pole wyboru, aby generować dodatkowe raporty we wskazanych walutach. Aby wyświetlić te raporty w przeglądarce sieci web, kliknij przycisk <strong>Waluta</strong> i wybierając walutę.</td>
</tr>
<tr class="even">
<td>Informacje o dacie niezapisane w definicji raportu</td>
<td><ul>
<li>Okres podstawowy</li>
<li>Rok podstawowy</li>
<li>Objęty okres</li>
</ul>
W definicji raportu są zapisywane tylko ustawienia domyślnego okresu podstawowego.</td>
</tr>
<tr class="odd">
<td>Informacje o dacie nie są zapisane w definicji raportu</td>
<td><ul>
<li>Data raportu</li>
<li>Domyślny okres podstawowy</li>
</ul></td>
</tr>
<tr class="even">
<td>Raporty w grupie</td>
<td>Dodawanie, usuwanie i zmienianie kolejności raportów w grupie raportów.
<ul>
<li>Aby dodać definicje raportów do grupy raportów, kliknij dwukrotnie grupę raportów, aby ją otworzyć, a następnie kliknij <strong>Dodaj</strong>. Wybierz raporty, które mają znaleźć się w grupie raportów, a następnie kliknij <strong>OK</strong>.</li>
<li>Aby usunąć raport z grupy raportów, wybierz go, a następnie kliknij <strong>Usuń</strong>.</li>
<li>Aby zmodyfikować kolejność, w jakiej raporty są generowane, wybierz raport na liście, a następnie kliknij przycisk <strong>Przenieś w górę</strong> lub <strong>Przenieś w dół</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Informacje dodatkowe
--------

[Microsoft Dynamics 365 dla operacji sprawozdawczość finansowa](financial-reporting-intro.md)


