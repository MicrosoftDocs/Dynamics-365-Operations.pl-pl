---
title: Praca z funkcją Wiadomości elektroniczne
description: Ten artykuł zawiera informacje dotyczące sposobu pracy z funkcją Wiadomości elektroniczne (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b61c119a06e1a7281d3adb67e043d2f7002cbea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880709"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Praca z funkcją Wiadomości elektroniczne

[!include [banner](../includes/banner.md)]

Podczas pracy na poziomie komunikatu strona **Wiadomości elektroniczne** (**podatek**\>**zapytania i raporty**\>**wiadomości elektroniczne**\>**Wiadomości elektroniczne**) jest bardziej użyteczna. Podczas pracy na poziomie zbiorów danych (element wiadomości), strona **Elementy wiadomości elektronicznych** (**Podatek** \> **Zapytania i raporty** \> **Wiadomości elektroniczne** \> **Elementy wiadomości elektronicznych**) jest bardziej użyteczna.

## <a name="electronic-messages"></a>Wiadomości elektroniczne

Strona **Wiadomości elektroniczne** przedstawia przetwarzanie, które dostępne w zależności od roli użytkownika. Role zabezpieczeń są skojarzone z przetwarzaniem w ustawieniach tego przetwarzania. Dla każdego dostępnego przetwarzania strona pokazuje wiadomości elektronicznych i informacje związane z nimi.

Skrócona karta **Wiadomości** pokazuje wiadomości elektroniczne dla wybranego przetwarzania. W zależności od stanu wybranej wiadomości i wstępnie zdefiniowanego przetwarzania możesz uruchomić niektóre akcje, wybierając przyciski nas siatką:

- **Nowy** – ten przycisk jest skojarzony z akcjami typu **Utwórz wiadomość**.
- **Usuń** — ten przycisk jest dostępny, jeśli jest zaznaczone pole wyboru **Zezwalaj na usuwanie** dla bieżącego stanu wybranej wiadomości.
- **Zbieranie danych** — ten przycisk jest skojarzony z typem akcji **wypełnienia rekordów**.
- **Generuj raport** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca eksportu raportowania elektronicznego**.
- **Wyślij raport** – ten przycisk jest skojarzony z akcjami typu **Usługa sieci web**.
- **Importuj raport** — ten przycisk jest skojarzony z akcjami typu **Import raportu elektronicznego**.
- **Aktualizuj stan** — ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca przetwarzania poziomu użytkownika** typu.
- **Element wiadomości** – otwórz stronę **Elementy wiadomości elektronicznej**.

Skrócona karta **Dziennik akcji** wyświetla informacje o wszystkich akcjach uruchomionych dla wybranej wiadomości. Jeśli akcja spowodowała błąd, informacje o błędzie są dołączane do powiązanego wiersza siatki. Aby przejrzeć informacje dotyczące błędu, wybierz wiersz w siatce, a następnie wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

Skrócona karta **Dodatkowe pola wiadomości** pokazuje wszystkie dodatkowe pola, które są zdefiniowane dla wiadomości w ustawieniach przetwarzania. Skrócona karta pokazuje także wartości z tych dodatkowych pól.

Skrócona karta **Elementy wiadomości** pokazuje wszystkie elementy wiadomości, które są powiązane z wybraną wiadomością. W zależności od stanu wybranego elementu wiadomości możesz uruchomić niektóre akcje, wybierając przyciski nas siatką:

- **Usuń** — ten przycisk jest dostępny, jeśli jest zaznaczone pole wyboru **Zezwalaj na usuwanie** dla bieżącego stanu wybranego elementu wiadomości.
- **Aktualizuj stan** — ten przycisk jest skojarzony z akcjami typu **Przetwarzanie przez użytkownika**.
- **Oryginalny dokument** — otwiera stronę, na której znajduje się oryginalny dokument dla elementu wybranej wiadomości.

Wszystkie raporty, które zostały już wygenerowane i odebrane dla wiadomości, są dołączone do tej wiadomości. Aby przejrzeć załączniki związane z wiadomością, wybierz wiadomość, a następnie wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

![Przycisk Załącznik](media/attachment-icon.png)

Strona **Załączniki** pokazane wszystkie załączniki, które są związane z wybraną wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

![Przycisk Otwórz](media/open-button.png)

Można także przejrzeć załączniki, które są związane z określoną akcją uruchomioną wcześniej dla danej wiadomości. Na stronie **Wiadomości elektroniczne** na skróconej karcie **Komunikaty** zaznacz wiadomość. Na skróconej **Dziennik akcji** karcie wybierz akcję, po czym naciśnij przycisk **Załącznik** (symbol spinacza) w prawym górnym rogu strony.

Można również uruchomić przez zaznaczenie całego przetwarzania lub po prostu określonej akcji, wybierając **Uruchom przetwarzanie** w okienku akcji.

## <a name="electronic-message-items"></a>Elementy wiadomości elektronicznych

Strona **Elementy wiadomości elektronicznych** przedstawia wszystkie elementy wiadomości i dziennika akcji, które zostały wykonywane dla każdego elementu wiadomości. Strona zawiera także dodatkowe pola, które są zdefiniowane dla elementów wiadomości oraz wartości tych dodatkowych pól.

W poniższej tabeli opisano pola znajdujące się na karcie **Elementy wiadomości**.

<table>
<thead>
<tr>
<th>Pole</th>
<th>opis</th>
</tr>
</thead>
<tbody>
<tr>
<td>Przetwarzanie</td>
<td>Nazwa przetwarzania, która została użyta do utworzenia elementu wiadomości.</td>
</tr>
<tr>
<td>Element wiadomości</td>
<td>Identyfikator elementu wiadomości. Identyfikator jest przypisywany automatycznie na podstawie numeru sekwencji <b>Elementu wiadomości</b> określonego na stronie <b>Parametry księgi głównej</b>.</td>
</tr>
<tr>
<td>Data elementu wiadomości</td>
<td>Data utworzenia elementu wiadomości.</td>
</tr>
<tr>
<td>Typ elementu wiadomości</td>
<td>Typ elementu wiadomości. Można skonfigurować kilka typów elementów wiadomości dla tego samego przetwarzanie (na przykład <b>Faktury przychodzące </b> i <b>Faktury wychodzące</b>). To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Stan elementu wiadomości</td>
<td><p>Rzeczywisty stan elementu wiadomości. Dostępne stany różnią się w zależności od typu elementu wiadomości. Oto kilka przykładów:</p>
<ul>
<li><b>Wypełnione</b> — rekord został dodany do tabeli elementów wiadomości.</li>
<li><b>Oceniane</b> — dodatkowe atrybuty zostały obliczone dla towaru wiadomości.</li>
<li><b>Zgłoszone</b> — element wiadomości został pomyślnie dodany do raportu.</li>
<li><b>Wykluczone</b> — Ten status jest przydatny, jeśli niektóre elementy wiadomości powinny zostać wykluczone z raportu przed jego eksportem.</li>
</ul>
</td>
</tr>
<tr>
<td>Data transmisji</td>
<td>W przypadku przetwarzania, które automatycznie przesyła wygenerowany raport poza system, data, kiedy wiadomość została przekazana.</td>
</tr>
<tr>
<td>Numer dokumentu</td>
<td>To pole jest wypełniane automatycznie na podstawie konfiguracji akcji wypełniania rekordu. To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Numer konta</td>
<td>Numer konta odbiorcy lub dostawcy (lub wartość innego pola, w zależności od pola, które jest określone w akcji Wypełnij rekordy). To pole może być wypełnione automatycznie tylko wtedy, gdy faktura jest dodawana do tabeli Elementy wiadomości.</td>
</tr>
<tr>
<td>Komunikat</td>
<td>Numer wiadomości. Numer jest przypisywany automatycznie na podstawie numeru sekwencji <b>Wiadomość</b> określonego na stronie <b>Parametry księgi głównej</b>.</td>
</tr>
<tr>
<td>Stan komunikatu</td>
<td>Rzeczywisty stan wiadomości elektronicznej.</td>
</tr>
<tr>
<td>Następna akcja</td>
<td>Następne akcje, które mogą być zainicjowane dla bieżącego stanu elementu wiadomości.</td>
</tr>
</tbody>
</table>

Karta **Dodatkowe pola** pokazuje dodatkowe pola dla elementu wybranej wiadomości i ich wartości.

### <a name="run-processing"></a>Uruchom przetwarzanie

W okienku akcji wybierz **Uruchom przetwarzanie**, aby uruchomić przetwarzania elementów wiadomości. Aby uruchomić określoną akcję w oknie dialogowym **Uruchom przetwarzanie** ustaw opcję **Wybierz akcję** na **tak**, a następnie wybierz odpowiednią akcję. Aby uruchomić całe przetwarzanie, zostaw opcję **Wybierz akcję** na **Nie**.

### <a name="generate-report"></a>Generuj raport

W okienku akcji wybierz pozycję **Utwórz raport**. Ten przycisk jest skojarzony z akcjami typu **Wiadomość dotycząca eksportu raportowania elektronicznego**.

### <a name="update-status"></a>Aktualizacja stanu

W okienku akcji wybierz **Aktualizacja stanu**, aby zaktualizować stan jednego lub kilku elementów wiadomości. W oknie dialogowym **Aktualizacja stanu** użyj skróconej karty **Rekordy do uwzględnienia** do wybierania elementów wiadomości do aktualizacji. Upewnij się, że poprawnie zdefiniowano kryteria wyboru, ponieważ stany elementów wiadomości zostaną zaktualizowane zgodnie z tymi kryteriami, początkowy stan wybranej akcji oraz wartość ustaloną w polu **Nowy stan**. Po zakończeniu aktualizacji stanu będzie trudno określić elementy, które właśnie zostały zaktualizowane. W związku z tym będzie trudno cofnąć aktualizacje stanu.

### <a name="electronic-messages"></a>Wiadomości elektroniczne

W okienku akcji wybierz **Wiadomości elektroniczne**, aby przejrzeć wiadomość elektroniczną powiązaną z pozycją wybranej wiadomości.

Można także przejrzeć pliki, które odpowiadają elementowi wiadomości. Wybierz pole **Wiadomość** dla elementu wiadomości lub wybierz **Wiadomości elektroniczne** w okienku akcji. Następnie, na stronie **Wiadomości elektroniczne** wybierz wiadomość, dla której chcesz przejrzeć pliki, po czym wybierz przycisk **załącznik** (symbol spinacza) w prawym górnym rogu strony.

Strona **Załączniki** pokazane załączniki, które są związane z wiadomością. Aby wyświetlić plik, wybierz go z listy po lewej stronie, a następnie wybierz **Otwórz** w okienku akcji.

### <a name="original-document"></a>Dokument oryginalny

W okienku akcji wybierz **Oryginalny dokument**, aby otworzyć oryginalny dokument dla elementu wybranej wiadomości.
