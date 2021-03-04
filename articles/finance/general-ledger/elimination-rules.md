---
title: Reguły eliminacji
description: Ten temat zawiera informacje o różnych regułach eliminacji i opcjach raportowania eliminacji.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdcfebad5329b8ac6f3507f2bc59f26cf70aae33
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446902"
---
# <a name="elimination-rules"></a>Reguły eliminacji

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o różnych regułach eliminacji i opcjach raportowania eliminacji.

Transakcje eliminacji są wymagane, gdy firma macierzysta współpracuje z przynajmniej jednym oddziałem firmy oraz korzysta ze skonsolidowanych raportów finansowych. Skonsolidowane sprawozdania finansowe muszą zawierać tylko transakcje między skonsolidowaną organizacją a innymi podmiotami spoza tej organizacji. Z tego względu transakcje między firmami, które znajdują się w tej samej organizacji, należy usunąć lub wyeliminować z księgi głównej, aby nie były wyświetlane w raportach finansowych. Istnieje wiele sposobów przygotowania raportu na temat eliminacji:

-   Reguły eliminacji mogą być tworzone i przetwarzane w firmie konsolidacji lub eliminacji.
-   Raporty finansowe mogą pokazywać konta i wymiary eliminacji w określonym wierszu lub kolumnie.
-   Odrębna osoba prawna może służyć do księgowania transakcji ręcznej do śledzenia eliminacji.

Temat poświęcony jest regułom eliminacji, które są przetwarzane w firmie konsolidacji i eliminacji. Można określić reguły eliminacji w celu utworzenia transakcji eliminacji w firmie określonej jako firma docelowa dla eliminacji. Ta firma docelowa jest znana jako firma z wpisami eliminacji. Arkusze eliminacji mogą być generowane albo podczas procesu konsolidacji, albo za pomocą propozycji arkusza eliminacji. Przed skonfigurowaniem reguł eliminacji należy zapoznać się z następującymi terminami:

-   **Źródłowa firma** — Firma, w której zostały zaksięgowane kwoty, które są eliminowane.
-   **Firma docelowa** — Firma, w której są księgowane reguły eliminacji.
-   **Firma z wpisami eliminacji** — Firma określona jako firma docelowa dla eliminacji.
-   **Firma skonsolidowana** — Firma utworzona na potrzeby raportowania wyników finansowych grupy firm. Dane finansowe firm są konsolidowane w ramach tej firmy, a następnie przy użyciu połączonych danych jest tworzony raport finansowy.

W poniższej tabeli przedstawiono typy transakcji, które być może trzeba będzie wyeliminować.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Typ transakcji</th>
<th>Przykład</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Wprowadzanie i fakturowanie zamówień sprzedaży (przetwarzanie scentralizowane)</td>
<td>Sprzedaż produktu odbiorcy w imieniu innej firmy w organizacji.</td>
</tr>
<tr class="even">
<td>Wprowadzanie i fakturowanie zamówień sprzedaży (międzyfirmowe/wewnątrzfirmowe)</td>
<td>Sprzedaż produktów między firmami w organizacji.</td>
</tr>
<tr class="odd">
<td>Zamówienia zakupu (przetwarzanie scentralizowane)</td>
<td>Zakup zapasów, materiałów, usług, środków trwałych i innych produktów u dostawcy w imieniu innej firmy w organizacji.</td>
</tr>
<tr class="even">
<td>Zarządzanie zapasami (międzyfirmowe/wewnątrzfirmowe)</td>
<td><ul>
<li>Przeniesienie zapasów jednej firmy do środków trwałych innej firmy w organizacji.</li>
<li>Przeniesienie zapasów jednej firmy do zapasów innej firmy w organizacji.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Śledzenie zapasów w transporcie</td>
<td>Przeniesienie towarów między magazynami w tej samej firmie, ale znajdującymi się w różnych lokalizacjach geograficznych.</td>
</tr>
<tr class="even">
<td>Scentralizowane przetwarzanie faktur rozrachunków z dostawcami</td>
<td>Rejestrowanie faktury w imieniu innej firmy w organizacji.</td>
</tr>
<tr class="odd">
<td>Scentralizowane przetwarzanie płatności rozrachunków z dostawcami</td>
<td>Płacenie za fakturę w imieniu innej firmy w organizacji.</td>
</tr>
<tr class="even">
<td>Zarządzanie gotówką i akcjami (przetwarzanie scentralizowane)</td>
<td><ul>
<li>Przetwarzanie płatności podatkowych, zwrotów podatku, należnych odsetek, pożyczek, zaliczek, wypłaconych dywidend oraz prowizji/tantiem.</li>
<li>Płacenie wydatków w imieniu innej firmy w organizacji. Faktura jest wprowadzana w księgach firmy docelowej, a użytkownik musi rozliczyć ją wzajemnie między firmami. Na przykład jedna firma płaci raport z wydatków pracownika w innej firmie. W tym przypadku raport z wydatków pracownika ma wydatki związane z inną firmą.</li>
<li>Przekazywanie gotówki z jednej firmy do innej w organizacji.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Rozrachunki z odbiorcami (przetwarzanie scentralizowane)</td>
<td>Przyjmowanie gotówki na podstawie faktury odbiorcy innej firmy i składanie czeku na konto bankowe tej firmy.</td>
</tr>
<tr class="even">
<td>Lista płac (przetwarzanie scentralizowane, międzyfirmowe/wewnątrzfirmowe)</td>
<td><ul>
<li>Dokonywanie płatności listy płac innej firmy. Na przykład firma wypłaca pensje według listy płac swoim pracownikom, ale realizuje zwrot kosztów dla pracowników innej firmy w tym przebiegu płatności. Lub jeśli pracownik jest zatrudniony na pół etatu w firmie A oraz na pół etatu w firmie B i otrzymuje w obu miejscach pracy inne świadczenia. W takich przypadkach płaca pracownika obejmuje płatności z obu firm. Oprócz wynagrodzeń mogą być także księgowane podatki, świadczenia, potrącenia i naliczenia związane z wynagrodzeniami.</li>
<li>Przenoszenie robocizny między działami lub oddziałami.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Środki trwałe (międzyfirmowe/wewnątrzfirmowe)</td>
<td>Przenoszenie środków trwałych do środków trwałych lub zapasów innej firmy.</td>
</tr>
<tr class="even">
<td>Alokacje (międzyfirmowe/wewnątrzfirmowe)</td>
<td>Przetwarzanie alokacji firmowych. Alokacje to działania dotyczące dowolnego konta podlegającego alokacji, niezależnie od modułu źródłowego.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Przykład
Twoja firma, czyli firma A, sprzedaje gadżety innej firmie w twojej organizacji, czyli firmie B. W poniższym przykładzie pokazano sposób, w jaki być może trzeba będzie wyeliminować transakcje między dwiema firmami:

-   Firma A sprzedaje gadżet, który kosztuje 10,00, firmie B za 10,00.
-   Firma A sprzedaje gadżet, który kosztuje 10,00, firmie B za 10,00 + 2,00 rzeczywistych kosztów wysyłki.
-   Firma A sprzedaje firmie B gadżet o wartości 10,00 w cenie 15,00 i otrzymuje marżę z tej sprzedaży.
-   Firma A sprzedaje firmie B gadżet o wartości 10,00 w cenie 15,00 i otrzymuje połowę marży z tej sprzedaży. Firma B otrzymuje drugą połowę marży ze sprzedaży. Zatem przychód jest podzielony. Podział przychodu stanowi zachętę do zamówienia z innej firmy w organizacji, a nie z zewnętrznej organizacji.

Wszystkie te transakcje tworzą transakcje międzyfirmowe, księgowane na kontach zobowiązań i należności. Ponadto w tych transakcjach mogą być uwzględniane kwoty podwyżek i obniżek, gdy kwota sprzedaży międzyfirmowej nie jest równa kosztowi sprzedanych towarów.

## <a name="set-up-elimination-rules"></a>Konfigurowanie reguł eliminacji
Podczas konfigurowania reguł eliminacji zalecamy utworzenie wymiaru finansowego specjalnie do celów eliminacji. Większość klientów nazywa ten wymiar Partner handlowy lub podobnie. Jeśli postanowisz nie używać wymiaru finansowego, to upewnij się, że masz konta główne przeznaczone tylko do transakcji międzyfirmowych. 

Ta konfiguracja eliminacji znajduje się w obszarze Ustawienia w module Konsolidacje. Po wprowadzeniu opisu reguły trzeba wybrać firmę, w której arkusza eliminacji będzie księgowany. Powinna to być firma, która ma wybraną opcję **Użyj na potrzeby procesu eliminacji finansowej** w ustawieniach firmy. 

W razie potrzeby można ustawić daty początku i końca obowiązywania reguły eliminacji. Należy ustawić opcję **Aktywne** na **Tak**, jeśli reguła ma być dostępna w procesie propozycji eliminacji. Wybierz arkusz, który ma typ **Eliminacja**.

Po określeniu podstawowych ustawień można zdefiniować faktyczne reguły przetwarzanego przez kliknięcie przycisku **Wiersze**. Możliwe są dwie opcje dla eliminacji: eliminowanie kwoty zmiany netto lub definiowanie stałej kwoty. 

Wybierz konto źródłowe. Można użyć gwiazdki (\*) jako symbolu wieloznacznego. Na przykład wartość 1\* spowodowałaby używanie jako źródła danych alokacji wszystkich kont rozpoczynających się od 1. 

Po wybraniu kont źródłowych ustawienie **Specyfikacja konta** określa konto z używanej firmy docelowej. Wybierz opcję **Źródło**, jeśli chcesz używać tego samego konta głównego zdefiniowanego w ustawieniu **Źródło**. Jeśli wybierzesz opcję **Zdefiniowany przez użytkownika**, należy określić konto docelowe. 

Specyfikacja wymiaru działa w ten sam sposób. Jeśli wybierzesz opcję **Źródło**, w firmie docelowej będą używane te same wymiary, jak w firmie źródłowej. Jeśli wybierzesz opcję **Zdefiniowany przez użytkownika**, będzie trzeba określić wymiary w firmie docelowej, klikając elementu menu **Docelowe wymiary**. 

Wybierz wymiary źródłowe i wymiary finansowe oraz wartości, które będą używane jako źródło eliminacji.

## <a name="process-elimination-transactions"></a>Przetwarzanie transakcje eliminacji
Istnieją dwa sposoby przetwarzania transakcji eliminacji: w procesie konsolidacji online lub poprzez utworzenie arkusza eliminacji i uruchomienie procesu propozycji eliminacji. W tej sekcji skupiono się na tworzeniu arkusza i wykonywaniu procesu eliminacji. 

W firmie zdefiniowanej jako firma eliminacji wybierz opcję **Arkusz eliminacji** w module Konsolidacje. Po wybraniu arkusza kliknij przycisk **Wiersze**. Propozycję można wygenerować, wybierając menu **Propozycje**, a następnie wybierając opcję **Propozycja eliminacji**.

Wybierz firmę będącą źródłem skonsolidowanych danych, a następnie wybierz regułę, którą chcesz przetwarzać. Wprowadź daty początkową i końcową określające, kiedy ma się zaczynać i kończyć wyszukiwanie kwot eliminacji. Pole **Data księgowania w księdze głównej** zawiera datę zaksięgowania arkusza w księdze głównej. Po kliknięciu przycisku **OK** można przejrzeć kwoty i zaksięgować arkusz.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]