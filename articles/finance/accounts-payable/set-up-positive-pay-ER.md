---
title: Konfigurowanie i generowanie plików płatności dodatnich za pomocą raportowania elektronicznego
description: W tym artykule wyjaśniono, jak skonfigurować płacę dodatnią za pomocą raportowania elektronicznego.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878226"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Konfigurowanie plików płatności dodatnich za pomocą raportowania elektronicznego

Ten artykuł wyjaśnia, jak skonfigurować płacę dodatnią i wygenerować pliki z płacą dodatnią za pomocą raportowania elektronicznego.

> [!NOTE] 
> Przed użyciem funkcji **Wygeneruj plik pozytywnej wypłaty bankowej** musisz najpierw odświeżyć listę podmiotów.
> Przejdź do szybkiej karty **Zarządzanie danymi > Import / Eksport > Parametry ramowe** 
> **Ustawienia encji**, wybierz **Odśwież listę encji**.


Konfigurowanie płatności dodatnich w celu generowania elektronicznej listy czeków dostarczanych do banku. Kiedy czek jest przedstawiany w banku, bank porównuje go z listą czeków. Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek. Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.

## <a name="security-for-positive-pay-files"></a>Zabezpieczenia plików płatności dodatnich
Pliki płatności dodatnich mogą zawierać poufne informacje na temat odbiorców płatności i kwot czeków. W związku z tym musisz podjąć odpowiednie środki bezpieczeństwa od momentu wygenerowania plików aż do ich odbioru przez bank. Pliki płatności dodatnich są pobierane do lokalizacji określonej przez przeglądarkę internetową. Ponieważ pliki płatności dodatnich mogą zawierać informacje poufne, ważne jest, aby tylko upoważnieni użytkownicy mieli dostęp umożliwiający generowanie i wyświetlanie tych informacji w usłudze Microsoft Dynamics 365 Finance. Poniższa tabela pomaga określić uprawnienia, które są wymagane.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Zadanie</th>
<th>Uprawnienie</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generowanie plików płatności dodatnich ze strony listy <strong>Konta bankowe</strong> lub strony <strong>Konta bankowe</strong>.</td>
<td><ul>
<li><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generowanie plików płatności dodatnich dla wielu firm i kont bankowych ze strony <strong>Generuj plik płatności dodatnich</strong>.</td>
<td><ul>
<li><strong>Obsługa informacji o bankowych płatnościach dodatnich</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Wyświetlanie plików płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Wyświetl informacje o bankowych płatnościach dodatnich wielu firm</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Potwierdzanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Potwierdź plik płatności dodatnich</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Wycofywanie pliku płatności dodatnich na stronie <strong>Podsumowanie pliku płatności dodatnich</strong>.</td>
<td><strong>Odwołaj plik płatności dodatnich</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-the-electronic-reporting-configuration"></a>Skonfiguruj konfigurację raportowania elektronicznego

1. Otwórz **Miejsca pracy \> Electroniczne Raportowanie**.
2. Na kafelku dla dostawcy konfiguracji **Microsoft** wybierz **Repozytoria**.
3. Wybierz opcję **Globalny**, a następnie wybierz opcję **Otwórz**.
4. Jeśli konieczne jest nawiązanie połączenia z repozytorium, wybierz niebieskie łącze w oknie dialogowym.
5. Na liście konfiguracji znajdź i wybierz **Pozytywny model wynagradzania \> Dodatni format wynagrodzenia**.
6. Na karcie **Wersje** FastTab wybierz najnowszą wersję, a następnie wybierz **Import**.

## <a name="set-up-a-positive-pay-format"></a>Konfigurowanie formatu płatności dodatnich

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Dodatni format wynagrodzenia**.
2. Wybierz pozycję **Nowy**.
3. Ustaw pola **Format płatności** i **Opis**.
4. Zaznacz pole **Ogólny elektroniczny format eksportu**.
5. Ustaw w polu **konfiguracji format eksportu** format płatności **dodatnich**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Przypisywanie formatu płatności dodatnich do konta bankowego
Dla każdego konta bankowego, dla którego chcesz wygenerować informacje o płatnościach dodatnich, należy przypisać format płatności dodatnich, który został określony w poprzedniej sekcji. Na stronie Konta bankowe zaznacz format płatności dodatnich odpowiadający kontu bankowemu. W polu **Data początkowa płatności dodatnich** wprowadź pierwszą datę dla generowania plików płatności dodatnich. 

>[!Important]
> Wprowadź datę w polu **Data rozpoczęcia wypłaty**. Jeśli pozostawisz puste pole, pierwszy wygenerowany plik z wypłatami pozytywnymi będzie zawierał wszystkie czeki, które zostały utworzone dla tego konta bankowego.

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Otwórz konto bankowe.
3. Na skróconej **karcie** Ogólne ustaw **format płatności dodatnich** na format utworzony wcześniej.
4. Ustaw w polu **Data rozpoczęcia płatności dodatnich** bieżącą datę.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Konfigurowanie sekwencji identyfikatorów plików płatności dodatnich
Każdy plik płatności dodatnich musi mieć unikatowy numer. Na stronie **Parametry zarządzania gotówką i bankiem** utwórz sekwencję numerów dla plików z wypłatami dodatnimi w zakładce **Sekwencje numerów**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generowanie pliku płatności dodatnich dla jednego konta bankowego
Można wygenerować plik płatności dodatnich dla pojedynczej firmy i pojedynczego konta bankowego. Informacje o generowaniu plików płatności dodatnich dla wielu firm i kont bankowych w tym samym czasie znajdują się w następnej sekcji. Aby wygenerować plik płatności dodatnich dla jednej firmy i jednego konta bankowego, ze strony **Konta bankowe** otwórz okno dialogowe **Generuj plik płatności dodatnich**. W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich. Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Otwórz konto bankowe, dla których ustawiono płatności dodatnie.
3. Wybierz opcję **Zarządzaj płatnościami \> Dodatnie wynagrodzenie \> Dodatnia kartoteka wynagrodzeń**.
4. Ustaw pole **Data graniczna**. Zostaną uwzględnione czeki wygenerowane wcześniej niż ta data.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generowanie pliku płatności dodatnich dla wielu kont bankowych
Aby wygenerować plik płatności dodatnich dla wielu kont bankowych, użyj zadania okresowego **plik płatności dodatnich**. Wybierz format pliku płatności dodatnich oraz określ, czy wygenerować plik dla wszystkich firm, czy tylko dla wybranej firmy. Można również wygenerować plik płatności dodatnich dla wszystkich kont bankowych używających określonego formatu płatności dodatnich albo tylko dla wybranego konta bankowego. W polu **Data graniczna** wprowadź ostatnią datę czeku do uwzględnienia w pliku płatności dodatnich. Wszystkie czeki, które jeszcze nie zostały uwzględnione w pliku płatności dodatnich do tej daty czeku, znajdą się w pliku.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Wyświetlanie wyników generowania pliku płatności dodatnich
Po wygenerowaniu pliku płatności dodatnich wyniki można obejrzeć na stronie **Podsumowanie pliku płatności dodatnich**. Aby wyświetlić szczegółowe informacje o poszczególnych czekach, należy przejść do strony szczegółów **Plik płatności dodatnich**.

## <a name="confirm-a-positive-pay-file"></a>Potwierdź plik płatności dodatnich
Po zapłaceniu czeków wymienionych w pliku płatności dodatnich, otrzymasz numer potwierdzenia z banku. Wtedy można potwierdzić plik płatności dodatnich. Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wprowadź potwierdzenie**. Po potwierdzeniu pliku płatności dodatnich następuje odnotowanie numeru potwierdzenia otrzymanego z banku.

## <a name="recall-a-positive-pay-file"></a>Odwoływanie pliku płatności dodatnich
Jeśli trzeba zmodyfikować plik płatności dodatnich, można go wycofać. Na stronie **Podsumowanie pliku płatności dodatnich** zaznacz plik płatności dodatnich, który ma stan **Utworzone**, a następnie wybierz akcję **Wycofaj**. Dla każdego czeku w pliku płatności dodatnich jest resetowane pole wskazujące, czy czek jest uwzględniony w pliku płatności dodatnich. Następnie można utworzyć nowy plik płatności dodatnich zawierający wycofany czek.


Wynikowy plik XML zostanie pobrany.
