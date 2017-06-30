---
title: Generowanie raportu finansowego
description: Ten temat zawiera informacje o generowaniu sprawozdania finansowego.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9b0d8fd9f5ae9d99f299cc71d7caef021ad3fb9d
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="generate-a-financial-report"></a>Generowanie raportu finansowego

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje o generowaniu sprawozdania finansowego. 

Aby wygenerować raport, otwórz definicję raportu, a następnie kliknij przycisk Generuj na pasku narzędzi. Okno Stan kolejki raportów otworzy się i wskaże lokalizację raportu w kolejce. Domyślnie wygenerowany raport zostanie otwarty w przeglądarce sieci web.
| ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**        |
|------------------------------------------------------------------------------------------------|
| Można generować raporty tylko do folderów i lokalizacji, do których masz uprawnienia dostępu. |

W poniższej tabeli wyjaśniono opcje dostępne do generowania raportów.

| Opcja                                                                                | Więcej informacji |
|---------------------------------------------------------------------------------------|----------------------|
| Konfigurowanie harmonogramu w celu automatycznego generowania raportu lub grupy raportów              |                      |
| Sprawdzanie brakujących kont lub danych w raporcie i sprawdzanie poprawności raportu |                      |

Podczas generowania raportu są używane opcje, które określono na kartach Definicja raportu. Karta Produkcja i dystrybucja pozwala określić lokalizację biblioteki raportów, która zapewnia prosty sposób udostępniania raportu.

## <a name="schedule-report-generation"></a> Generowanie raportu planu
Wiele firm ma podstawowy zbiór raportów, które są uruchamiane w zaplanowanych okresach, w celu dostosowania ich procesów biznesowych. Można zaplanować raport do generowania regularnego, np. codziennie, co tydzień, co miesiąc lub co roku. Może to być pojedynczy raport lub grupa raportów, która obejmuje wiele firm. Należy wprowadzić swoje poświadczenia dla każdej z firm, które zostaną określone, np. takie jak w definicji drzewa raportowania. Jeśli poświadczenia nie są prawidłowe, raport wyświetli tylko informacje, że masz uprawnienia dostępu, takie jak firma w której jesteś zalogowany w danej chwili. Informacje o danych wyjściowych są odczytywane najpierw z grupy raportów, a następnie z poszczególnych raportów.

Tworzone i zapisywane raporty są wyświetlane w okienku nawigacji w obszarze Harmonogramy raportów. Można utworzyć foldery, aby zorganizować raporty. Jeśli nie działa jeden raport w harmonogramie, wszystkie pozostałe raporty będą dalej działały.
| ![Ważne](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Ważne")**Ważne**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Do tworzenia, modyfikowania i usuwania harmonogramów raportów wymagana jest rola projektanta lub administratora. Po uruchomieniu raportu poświadczenia użytkownika, który utworzył harmonogram, są używane do generowania raportu. |

### <a name="create-a-report-schedule"></a>Tworzenie harmonogramu raportu

1.  W Projektancie raportów w menu Plik kliknij przycisk Nowy, a następnie wybierz opcję Harmonogram raportu. Zostanie otwarte okno dialogowe Nowy harmonogram raportu.
2.  W obszarze Ustawienia wybierz pojedynczy raport lub grupę raportów do zaplanowania. Dostępne są tylko raporty lub grupy raportów dla wybranej firmy lub elementu konstrukcyjnego, w której użytkownik jest aktualnie zalogowany.
3.  Wybierz pole wyboru Aktywne, aby włączyć funkcję harmonogramu raportów. Tylko twórca raportu lub administrator można uaktywnić lub dezaktywować harmonogram raportu.
4.  Kliknij przycisk Uprawnienia, aby wprowadzić poświadczenia firmy. Domyślnie dane logowania użytkownika są używane dla firmy, której użytkownik jest zalogowany. Jeśli innych firm są uwzględnione, np. w definicjach drzewa raportowania, wybierz Użyj osobnych poświadczeń, a następnie wprowadź poświadczenia dla firmy, uwzględnionej w harmonogramie raportu. Można wybrać uwierzytelnianie systemu Windows lub wpisać nazwę użytkownika i hasło dla każdej firmy. Zaznacz pole wyboru Zapisz poświadczenia, aby zapisać poświadczenia dla tych firm, a następnie kliknij przycisk OK, aby zamknąć okno dialogowe.
5.  W obszarze Częstotliwość w polu Początek cyklu wybierz dzień, gdy harmonogram ma się uruchomić. Domyślnie jest zaznaczona bieżąca data systemowa komputera klienckiego.
6.  W polu Uruchomić raport o wybierz godzinę uruchomienia raportu. Po wprowadzeniu godziny, która jest wcześniejsza niż bieżący czas systemowy, raport zostanie uruchomiony na następny dzień według harmonogramu.
7.  W obszarze Wzorzec cyklu określ częstotliwość uruchamiania raportu. Domyślnie wybrana jest opcja Codziennie z wartością 1 dla opcji Interwał (w dniach). Inne dostępne opcje to Co tydzień, Co miesiąc i Co rok.
8.  W obszarze Zakres cyklu wybierz, kiedy raport ma przestać być generowany.
    -   Brak daty zakończenia — harmonogram raportu działa w nieskończoność.
    -   Ustawianie liczby wystąpień — harmonogram raportu działa przez określoną ilość razy, a następnie jest dezaktywowany.
    -   Koniec do — harmonogram raportu kończy się w określonym dniu.

9.  Kliknij Zapisz na pasku narzędzi. W oknie dialogowym Zapisz jako wprowadź unikatową nazwę i opis dla harmonogramu raportu.

Do kopiowania harmonogramu raportu wymagana jest rola projektanta lub administratora. Nawet wtedy, gdy administrator zmienia harmonogram raportu, raport przyjmuje poświadczenia użytkownika, który utworzył raport.
### <a name="copy-a-report-schedule"></a>Kopiowanie harmonogramu raportu

1.  W Projektancie raportów, kliknij Harmonogramy raportów w okienku nawigacji i otwórz raport planowanie do skopiowania.
2.  W menu Plik kliknij Zapisz jako, a następnie wprowadź nową nazwę i opis dla harmonogramu w oknie dialogowym Zapisz jako. Kliknij OK, a nowy harmonogram jest wyświetlany w okienku nawigacji.
3.  W nowym harmonogramie zmień pola i informacje według potrzeb, a następnie kliknij Zapisz na pasku narzędzi lub kliknij Zapisz w menu Plik.

Aby usunąć harmonogram raportu, musisz być właścicielem harmonogramu raportu lub mieć rolę administratora.
### <a name="delete-a-report-schedule"></a>Usuwanie harmonogramu raportu

1.  W Projektancie raportów kliknij Harmonogramy raportów w okienku nawigacji.
2.  Wybierz harmonogram raportu do usunięcia, a następnie kliknij przycisk Usuń lub naciśnij klawisz Delete.
3.  W oknie dialogowym weryfikacji usuwania kliknij Tak, aby trwale usunąć harmonogramu raportu. Jeśli nie masz uprawnień do usuwania harmonogramu, wyświetlany jest komunikat, a raport nie jest usuwany.

### <a name="credentials-and-report-schedules"></a>Poświadczenia i harmonogramy raportów

Jeśli nie wprowadzisz poświadczeń, które są wymagane dla wszystkich firm uwzględnionych w raportach, podczas zapisywania harmonogramu raportu wyświetlony zostanie następujący komunikat: „Wprowadź poświadczenia dla firm, które są zawarte w harmonogramie tego raportu. Kliknij przycisk Uprawnienia, aby wprowadzić poświadczenia”.

Na przykład Phyllis loguje się do Firmy A za pomocą swojego loginu i hasła. Tworzy harmonogram dla raportu, który używa definicji drzewa raportowania do zbierania danych z wielu firm. Po zapisaniu tego harmonogramu raportu, Phyllis otrzymuje monit o podanie poświadczeń dla innych firm, które są określone w definicji drzewa raportowania. Po upływie limitu czasu poświadczenia, odpowiednie raporty w harmonogramie raportu nie są generowane do momentu aż poświadczenia zostaną zaktualizowane. O konieczności aktualizacji uprawnień informuje komunikat wyświetlany w kolejce raportów. Harmonogram raportu nie powiedzie się, jeśli wystąpi którykolwiek z następujących scenariuszy (ponieważ wymagają one poświadczeń):
-   Nowa firma została dodana do drzewa raportu dla konkretnego raportu.
-   Raport w grupie raportów został zmodyfikowany.
-   Nowy raport dla dodatkowej firmy został dodany do grupy raportów.

Aby kontynuować, kliknij przycisk Uprawnienia w oknie dialogowym Planowanie raportu, a następnie wprowadź odpowiednie poświadczenia.

## <a name="missing-account-analysis-feature"></a> Funkcja analizy brakujących kont
Można wyszukiwać konta finansowe i wymiary, których może brakować we wszystkich definicjach wierszy, definicjach drzew raportowania i definicjach raportów w grupie bloków konstrukcyjnych. Jest to przydatne, jeśli tworzysz lub aktualizujesz kilka kont lub bloków konstrukcyjnych w krótkim okresie, a chcesz zweryfikować, że wszystkie nowe informacje są uwzględnione w raportach.

Brakujące konta są określane przy użyciu najniższej i najwyższej wartości z definicji wiersza lub definicji drzewa raportowania. Następnie program wyświetla listę kont, których nie ma w definicji wiersza lub definicji drzewa raportowania, ale które występują w danych finansowych. Jeśli brakujące konto jest większe lub mniejsze od wartości w definicji wiersza, to konto nie jest uwzględniane na liście brakujących kont.
| ![Porada](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Porada")**Porada**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| Na potrzeby sprawdzania ten proces powinien być uruchomiony przed wygenerowaniem miesięcznych raportów i podczas tworzenia bloków konstrukcyjnych. |

W raportach, które mają zakresy wartości, jest mniejsze prawdopodobieństwo brakujących kont. Jeśli to możliwe, używaj zakresów w blokach konstrukcyjnych, aby dodawać nowe konta podczas ich tworzenia. Jeśli jakikolwiek raport jest ustawiony na firmę @ANY, możesz zalogować się do określonej firmy i uruchomić analizę brakujących kont dla tej firmy.
| ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Po dodaniu nowej firmy należy ją dodać do drzew raportowania we wszelkich istniejących raportach. W przeciwnym razie firma nie zostanie uwzględniona w analizie brakujących kont. |

### <a name="run-missing-account-analysis"></a>Uruchamianie analizy brakujących kont

1.  W Projektancie raportów kliknij Narzędzia, a następnie kliknij Analizy brakujących kont.
2.  W polu Filtr firmy wybierz firmę, aby filtrować wyniki, lub wybierz Wszystkie (bez filtrowania), aby wyświetlić wyniki z wszystkich dostępnych firm.
3.  W polu Filtr wymiaru wybierz wymiar, aby filtrować wyniki, lub wybierz Wszystkie (bez filtrowania), aby wyświetlić wszystkie informacje dla wszystkich dostępnych wymiarów.
4.  W polu Grupuj wg wybierz opcję sortowania wyników. Można sortować wyniki na podstawie bloku konstrukcyjny, którego dotyczą, lub według zestawów wymiarów i wartości.
5.  Przejrzyj wyświetlane wyniki. Gdy wybierzesz element w górnym okienku, dolne okienko wyświetli dodatkowe informacje o wyjątku. Obejmuje to powiązane wymiary, wartości i raporty.
6.  Aby otworzyć element, którego dotyczy problem, kliknij skojarzoną ikonę widoczną w okienku listy, lub kliknij element prawym przyciskiem myszy i wybierz Otwórz. Aby zaznaczyć wiele elementów, przytrzymaj klawisz Ctrl podczas zaznaczania elementów w dolnym okienku.
7.  Jeśli analiza zwróci wartości, bloki konstrukcyjne lub raporty, których nie powinno w niej być, kliknij element prawym przyciskiem myszy i wybierz Wyklucz lub zaznacz pole wyboru Wykluczyć obok elementu, aby usunąć go z listy. Wykluczone elementy nie są uwzględniane podczas odświeżania listy. Aby zaznaczyć wiele elementów, przytrzymaj klawisz Ctrl podczas zaznaczania elementów w dolnym okienku. Aby wyświetlić wszystkie elementy, w tym wszystkie wyniki, które wcześniej zostały wykluczone z analizy, zaznacz pole wyboru Pokaż wykluczone bloki konstrukcyjne i wartości, a następnie kliknij Odśwież.
8.  Kliknij Odśwież, aby odświeżyć wyjątki, które zostały rozwiązane. Kliknij Tak, aby wykonać pełne odświeżenie wszystkich wyników, lub kliknij przycisk Nie, aby wykonać częściowe odświeżenie wskazanych elementów.
    | ![Uwaga](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Uwaga")**Uwaga**                    |
    |------------------------------------------------------------------------------------------------------------|
    | Formularz jest automatycznie odświeżany po jego otwarciu, chyba że formularz został otwarty w ciągu ostatnich 15 minut. |

9.  Gdy problem zostanie rozwiązany, kliknij OK, aby zamknąć okno dialogowe.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Skróty klawiaturowe dla analizy brakujących kont
Po uruchomieniu analizy brakujących kont dostępne są następujące skróty klawiaturowe.

| Funkcja                           | Użyj tego skrótu klawiaturowego |
|--------------------------------------|----------------------------|
| Filtruj według firm                    | Alt+C                      |
| Filtruj według wymiarów                  | Alt+D                      |
| Wybierz pole Grupuj wg            | Alt+G                      |
| Pokaż wykluczone bloki i wartości      | Alt+S                      |
| Odśwież wyniki                      | Alt+R                      |
| Wyklucz wybrany blok konstrukcyjny  | Alt+X                      |
| Wyklucz wybraną definicję wiersza  | Ctrl+B                     |
| Wyklucz wybraną wartość wymiaru | Ctrl+D                     |
| Otwórz wybraną definicję raportu  | Ctrl+R                     |
| Otwórz wybraną definicję wiersza     | Ctrl+O                     |

 
<a name="see-also"></a>Informacje dodatkowe
--------

[Raporty finansowe](financial-reporting-intro.md)

[Interfejs Projektanta raportów](report-designer-interface.md)



