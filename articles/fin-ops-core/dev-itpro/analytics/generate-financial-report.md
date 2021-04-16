---
title: Generowanie raportów finansowych
description: Ten temat zawiera informacje o generowaniu sprawozdania finansowego.
author: jinniew
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c6cde37124d4a3337bca2a9b445af5fdfd87f453
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750017"
---
# <a name="generate-financial-reports"></a>Generowanie raportów finansowych

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o generowaniu sprawozdania finansowego.

Aby wygenerować raport, otwórz definicję raportu, a następnie wybierz przycisk **Generuj** na pasku narzędzi. Strona **Stan kolejki raportów** otworzy się i wskaże lokalizację raportu w kolejce. Domyślnie wygenerowany raport zostanie otwarty w przeglądarce sieci web.

Są dostępne następujące opcje generowania raportów:

- Konfigurowanie harmonogramu w celu automatycznego generowania raportu lub grupy raportów
- Sprawdzanie brakujących kont lub danych w raporcie i sprawdzanie poprawności raportu

Podczas generowania raportu są używane opcje, które określono na kartach Definicja raportu.

## <a name="generate-a-financial-report"></a>Generowanie raportu finansowego

Aby wygenerować raport finansowy za pomocą, wybierz kolejno opcje **Księga główna** \> **Zapytania i raporty** \> **Raporty finansowe**.

- Wybierz raport do wygenerowania i wybierz opcję **Generuj**.
- Wypełnij pole **Data raportu** i wybierz przycisk **OK**.

Po wygenerowaniu raportu, raport będzie dostępny do wyświetlenia w sekcji **Raporty**.

Można wybrać dla raportu opcję **Wyświetl** lub **Usuń**.

Aby wygenerować raport za pomocą **Projektanta raportów**, otwórz definicję raportu, a następnie wybierz przycisk **Generuj** na pasku narzędzi. Strona **Stan kolejki raportów** otworzy się i wskaże lokalizację raportu w kolejce. Domyślnie wygenerowany raport zostanie otwarty w przeglądarce sieci web.

## <a name="report-groups"></a>Grupy raportów

Grupy raportów to efektywny sposób generowania kilku raportów jednocześnie. Przypuśćmy na przykład, że wiadomo, że na koniec miesiąca użytkownicy będą generować osiem raportów co miesiąc. Utwórz grupę raportów i zamiast wybierać opcję **Generuj** dla każdego z ośmiu raportów w grupie, możesz wybrać opcję **Generuj** dla grupy raportów, a w jednym kroku zostanie wygenerowanych osiem raportów. Po wygenerowaniu raportów z wybranej grupy raportów można przejść do widoku **Raporty finansowe** (**Księga główna > Zapytanie i raporty > Raporty finansowe**), aby wyświetlić poszczególne raporty. Wykonaj następujące kroki, aby skonfigurować grupę raportów.

1. W Projektancie raportów wybierz **Grupy raportów**. 
2. Wybierz istniejące definicje raportów do dołączyć do grupy raportów. 
3. Wybierz ustawienia zastępowania firmy, szczegółów i daty z każdego raportu, który zostanie uwzględniony w grupie.
   Zaleca się ustawienie poziomu **Firma**, **Okres**, **Rok** i **Szczegóły** dla każdego raportu. 
4. Zapisz grupę raportów.

## <a name="schedule-report-generation"></a>Planowanie generowania raportów
W wielu przedsiębiorstwach istnieje pewien podstawowy zbiór raportów, które są tworzone według określonego harmonogramu dopasowanego do potrzeb procesów biznesowych. Można zaplanować raport do generowania regularnego, np. codziennie, co tydzień, co miesiąc lub co roku. Sesja może obejmować jeden raport albo grupę raportów dla kilku przedsiębiorstw. Dla każdej uwzględnionej firmy, na przykład wpisanej w definicji drzewa raportowania, trzeba wprowadzić poświadczenia dostępu. Jeśli poświadczenia nie są prawidłowe, raport wyświetli tylko informacje, że masz uprawnienia dostępu, takie jak firma w której jesteś zalogowany w danej chwili. Informacje o danych wyjściowych są odczytywane najpierw z grupy raportów, a następnie z poszczególnych raportów.

Tworzone i zapisywane raporty są wyświetlane w okienku nawigacji w obszarze Harmonogramy raportów. W celu uporządkowania raportów można tworzyć foldery. Pominięcie generowania określonego raportu w harmonogramie nie wpływa w żaden sposób na pozostałe raporty.

> [!IMPORTANT]
> Aby móc tworzyć, modyfikować i usuwać harmonogramy raportów, trzeba pełnić rolę projektanta lub administratora. Po uruchomieniu raportu poświadczenia użytkownika, który utworzył harmonogram, są używane do generowania raportu.

### <a name="create-a-report-schedule"></a>Tworzenie harmonogramu raportu

1. W Projektancie raportów w menu **Plik** wybierz przycisk **Nowy**, a następnie wybierz opcję **Harmonogram raportu**. Zostanie otwarte okno dialogowe **Nowy harmonogram raportu**.
2. W obszarze **Ustawienia** wybierz pojedynczy raport lub grupę raportów do zaplanowania. Masz dostęp tylko do raportów/grup raportów dotyczących firmy lub zbioru modułów konstrukcyjnych, gdzie obecnie jesteś zalogowanym użytkownikiem.
3. Wybierz pole wyboru **Aktywne**, aby włączyć funkcję harmonogramu raportów. Aktywacji i dezaktywacji harmonogramu raportu może dokonywać wyłącznie jego twórca lub administrator.
4. Wybierz przycisk **Uprawnienia**, aby wprowadzić poświadczenia firmy. Domyślnie są używane poświadczenia logowania do firmy, gdzie obecnie jesteś zalogowanym użytkownikiem. Jeśli innych firm są uwzględnione, np. w definicjach drzewa raportowania, wybierz **Użyj osobnych poświadczeń**, a następnie wprowadź poświadczenia dla firmy, uwzględnionej w harmonogramie raportu. Można wybrać **Uwierzytelnianie systemu Windows** lub wpisać nazwę użytkownika i hasło dla każdej firmy. Zaznacz pole wyboru **Zapisz poświadczenia**, aby zapisać poświadczenia dla tych firm, a następnie wybierz przycisk **OK**, aby zamknąć okno dialogowe.
5. W obszarze **Częstotliwość** w polu **Początek cyklu** wybierz dzień, gdy harmonogram ma się uruchomić. Domyślnie jest ustawiana bieżąca data systemowa z komputera klienckiego.
6. W polu **Uruchomić raport o** wybierz godzinę uruchomienia raportu. Jeśli wprowadzisz godzinę wcześniejszą niż bieżąca godzina systemowa, raport zostanie po raz pierwszy wykonany w następnym zaplanowanym dniu.
7. W obszarze **Wzorzec cyklu** określ częstotliwość uruchamiania raportu. Domyślnie wybrana jest opcja **Codziennie** z wartością 1 dla opcji Interwał (w dniach). Inne dostępne opcje to Co tydzień, Co miesiąc i Co rok.
8. W obszarze Zakres cyklu określ długość okresu, przez jaki raport ma być generowany.

    - **Brak daty zakończenia** — harmonogram raportu działa w nieskończoność.
    - **Ustawianie liczby wystąpień** — harmonogram raportu działa przez określoną ilość razy, a następnie jest dezaktywowany.
    - **Koniec do** — harmonogram raportu kończy się w określonym dniu.

9. Wybierz opcję **Zapisz**. W oknie dialogowym **Zapisz jako** wprowadź unikatową nazwę i opis dla harmonogramu raportu.

Do kopiowania harmonogramu raportu wymagana jest rola projektanta lub administratora. Nawet wtedy, gdy administrator zmienia harmonogram raportu, raport przyjmuje poświadczenia użytkownika, który utworzył raport.

### <a name="copy-a-report-schedule"></a>Kopiowanie harmonogramu raportu

1. W Projektancie raportów, wybierz **Harmonogramy raportów** w okienku nawigacji i otwórz raport planowanie do skopiowania.
2. W menu **Plik** wybierz **Zapisz jako**, a następnie wprowadź nową nazwę i opis dla harmonogramu w oknie dialogowym **Zapisz jako**. Wybierz **OK**, a nowy harmonogram jest wyświetlany w okienku nawigacji.
3. W nowym harmonogramie zmień pola i informacje według potrzeb, a następnie wybierz **Zapisz** na pasku narzędzi lub wybierz **Zapisz** w menu **Plik**.

Aby usunąć harmonogram raportu, musisz być właścicielem harmonogramu raportu lub mieć rolę administratora.

### <a name="delete-a-report-schedule"></a>Usuwanie harmonogramu raportu

1. W Projektancie raportów wybierz **Harmonogramy raportów** w okienku nawigacji.
2. Wybierz harmonogram raportu do usunięcia, a następnie wybierz przycisk **Usuń** lub naciśnij klawisz **Delete**.
3. W oknie dialogowym weryfikacji usuwania wybierz **Tak**, aby trwale usunąć harmonogramu raportu. Jeśli nie masz uprawnień do usuwania harmonogramu, wyświetlany jest komunikat, a raport nie jest usuwany.

### <a name="credentials-and-report-schedules"></a>Poświadczenia i harmonogramy raportów

Jeśli nie wprowadzisz poświadczeń, które są wymagane dla wszystkich firm uwzględnionych w raportach, podczas zapisywania harmonogramu raportu wyświetlony zostanie następujący komunikat: „Wprowadź poświadczenia dla firm, które są zawarte w harmonogramie tego raportu. Kliknij przycisk Uprawnienia i wprowadź poświadczenia”.

Na przykład użytkownik loguje się w Firmie A przy użyciu swojej nazwy logowania i hasła. Użytkownik tworzy harmonogram dla raportu, który używa definicji drzewa raportowania do zbierania danych z wielu firm. Podczas zapisywania harmonogramu użytkownik zobaczy monit o wprowadzenie poświadczeń logowania do innych firm wymienionych w definicji drzewa raportowania. Po upływie limitu czasu poświadczenia, odpowiednie raporty w harmonogramie raportu nie są generowane do momentu aż poświadczenia zostaną zaktualizowane. O konieczności aktualizacji uprawnień informuje komunikat wyświetlany w kolejce raportów. Harmonogram raportu nie powiedzie się, jeśli wystąpi którykolwiek z następujących scenariuszy (ponieważ wymagają one poświadczeń):

- Nowa firma została dodana do drzewa raportu dla konkretnego raportu.
- Zmodyfikowanie raportu w drzewie raportów.
- Dodanie do grupy raportów nowego raportu obejmującego dodatkową firmę.

Aby kontynuować, wybierz przycisk **Uprawnienia** w oknie dialogowym **Planowanie raportu**, a następnie wprowadź odpowiednie poświadczenia.

## <a name="missing-account-analysis-feature"></a>Funkcja analizy brakujących kont
Można wyszukiwać konta finansowe i wymiary, których może brakować we wszystkich definicjach wierszy, definicjach drzew raportowania i definicjach raportów w grupie bloków konstrukcyjnych. Jest to przydatne, jeśli tworzysz lub aktualizujesz kilka kont lub bloków konstrukcyjnych w krótkim okresie, a chcesz zweryfikować, że wszystkie nowe informacje są uwzględnione w raportach.

Brakujące konta są określane przy użyciu najniższej i najwyższej wartości z definicji wiersza lub definicji drzewa raportowania. Następnie program wyświetla listę kont, których nie ma w definicji wiersza lub definicji drzewa raportowania, ale które występują w danych finansowych. Jeśli numer brakującego konta jest większy lub mniejszy od wartości określonych w definicji wiersza, konto nie jest uwzględniane na liście brakujących kont.

> [!TIP]
> Zalecane jest, aby w ramach sprawdzania poprawności uruchamiać tę procedurę przed generowaniem raportów miesięcznych oraz podczas tworzenia nowych modułów konstrukcyjnych.

W raportach, które mają zakresy wartości, jest mniejsze prawdopodobieństwo brakujących kont. Jeśli to możliwe, używaj zakresów w blokach konstrukcyjnych, aby dodawać nowe konta podczas ich tworzenia. Jeśli w definicji raportu ustawiono dla firmy wartość @ANY, można zalogować się do określonej firmy i uruchomić dla niej analizę brakujących kont.

> [!NOTE]
> Po dodaniu nowej firmy należy ją dodać do drzew raportowania we wszelkich istniejących raportach. W przeciwnym razie firma nie zostanie uwzględniona w analizie brakujących kont.

### <a name="run-missing-account-analysis"></a>Uruchamianie analizy brakujących kont

1. W Projektancie raportów wybierz **Narzędzia**, a następnie wybierz **Analizy brakujących kont**.
2. W polu **Filtr firmy** wybierz firmę, aby filtrować wyniki, lub wybierz **Wszystkie (bez filtrowania)**, aby wyświetlić wyniki z wszystkich dostępnych firm.
3. W polu **Filtr wymiaru** wybierz wymiar, aby filtrować wyniki, lub wybierz **Wszystkie (bez filtrowania)**, aby wyświetlić wszystkie informacje dla wszystkich dostępnych wymiarów.
4. W polu **Grupuj wg** wybierz opcję sortowania wyników. Wyniki można sortować zgodnie z modułem konstrukcyjnym, którego to dotyczy, lub według zestawów wymiarów i wartości.
5. Przegląd wyświetlanych wyników. Gdy w górnym okienku zostanie zaznaczony element, w dolnym okienku pojawią się dodatkowe informacje o wyjątku. Obejmują one powiązane wymiary, wartości i raporty.
6. Aby otworzyć element, którego dotyczy problem, wybierz skojarzoną ikonę widoczną w okienku listy, lub kliknij element prawym przyciskiem myszy i wybierz **Otwórz**. Aby zaznaczyć wiele elementów, przytrzymaj klawisz **Ctrl** podczas zaznaczania elementów w dolnym okienku.
7. Jeśli analiza zwróci wartości, bloki konstrukcyjne lub raporty, których nie powinno w niej być, kliknij element prawym przyciskiem myszy i wybierz **Wyklucz** lub zaznacz pole wyboru **Wykluczyć** obok elementu, aby usunąć go z listy. Wykluczone elementy nie są uwzględniane podczas odświeżania listy. Aby zaznaczyć wiele elementów, przytrzymaj klawisz **Ctrl** podczas zaznaczania elementów w dolnym okienku. Aby wyświetlić wszystkie elementy, w tym wcześniej wykluczone z analizy, zaznacz pole wyboru **Pokaż wykluczone moduły konstrukcyjne i wartości**, a następnie kliknij przycisk **Odśwież**.
8. Wybierz **Odśwież**, aby odświeżyć wyjątki, które zostały rozwiązane. Wybierz **Tak**, aby wykonać pełne odświeżenie wszystkich wyników, lub wybierz przycisk **Nie**, aby wykonać częściowe odświeżenie wskazanych elementów.

    > [!NOTE]
    > Formularz jest automatycznie odświeżany przy otwieraniu, chyba że był otwarty w ciągu ostatnich 15 minut.

9. Gdy problem zostanie rozwiązany, wybierz **OK**, aby zamknąć okno dialogowe.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Skróty klawiaturowe dla analizy brakujących kont
Po uruchomieniu analizy brakujących kont dostępne są następujące skróty klawiaturowe.

| Funkcja                           | Naciśnij klawisz  |
|--------------------------------------|----------------------------|
| Filtruj według firm                    | Alt+C                      |
| Filtruj według wymiarów                  | ALT+D                      |
| Wybierz pole Grupuj wg            | Alt+G                      |
| Pokaż wykluczone moduły i wartości      | Alt+S                      |
| Odśwież wyniki                      | Alt+R                      |
| Wyklucz wybrany moduł konstrukcyjny  | Alt+X                      |
| Wyklucz wybraną definicję wiersza  | Ctrl+B                     |
| Wyklucz wybraną wartość wymiaru | Ctrl+D                     |
| Otwórz wybraną definicję raportu  | Ctrl+R                     |
| Otwórz wybraną definicję wiersza     | Ctrl+O                     |


## <a name="additional-resources"></a>Dodatkowe zasoby

[Raporty finansowe](financial-reporting-intro.md)

[Interfejs Projektanta raportów](report-designer-interface.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
