---
title: Zamykanie roku obrachunkowego
description: Ta procedura prowadzi przez proces zamknięcia roku, który przenosi salda do nowego roku obrachunkowego.
author: aprilolson
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8eb36cb856d191d64561060e7de4a1f9fd947882
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717482"
---
# <a name="close-the-fiscal-year"></a>Zamykanie roku obrachunkowego

[!include [banner](../../includes/banner.md)]

Ta procedura prowadzi przez proces zamknięcia roku, który przenosi salda do nowego roku obrachunkowego.


## <a name="validate-year-end-close-parameters"></a>Sprawdzanie poprawności parametrów zamknięcia na koniec roku
1. Przejdź do **Okienko nawigacji > Moduły > Księga główna > Ustawienia księgi > Parametry księgi głównej**.
2. Rozwiń sekcję **Zamknięcie roku obrachunkowego**.
3. Zaznacz wartość **Tak** lub **Nie** dla opcji **Usuwanie transakcji zamknięcia roku podczas przenoszenia**.
    
To ustawienie jest ważne, jeśli rok obrachunkowy został już zamknięty, a jest ponownie wykonywane zamknięcie na koniec roku. Jeśli zostanie ustawione na **Tak**, załącznik poprzedniego zamknięcia na koniec roku zostanie usunięty, a zostanie utworzony nowy załącznik dla sald początkowych wszystkich kont. Jeśli ustawisz wartość **Nie**, poprzedni załącznik pozostanie, a nowy załącznik zostanie utworzony tylko dla zapisów korygujących, które zostały zaksięgowane po ostatnim zamknięciu na koniec roku.

4. Zaznacz wartość **Tak** lub **Nie** dla opcji **Tworzenie transakcji zamknięcia w trakcie przeniesienia**.

Jeśli ustawisz wartość **Tak**, tworzone są dwie transakcje. Jeden załącznik jest tworzony w zamykanym roku obrachunkowym w celu wyzerowania wszystkich sald kont księgowych rachunku zysków i strat, a drugi załącznik jest tworzony w następnym roku obrachunkowym dla sald początkowych. Jeśli ustawisz wartość **Nie**, jest tworzony jeden załącznik w następnym roku obrachunkowym dla sald początkowych.  

5. Zaznacz wartość **Tak** lub **Nie** dla opcji **Ustaw stan roku obrachunkowego na trwale zamknięty**.

Jeśli ustawisz wartość **Tak**, stan roku obrachunkowego zostanie ustawiony na Trwale zamknięty. Ponieważ trwale zamkniętego roku nie można otworzyć ponownie, byłoby najlepszym rozwiązaniem, aby ustawić tę opcję na wartość **Nie**.  

6. Zaznacz wartość **Tak** lub **Nie** dla opcji mówiącej o tym, czy **numer załącznika musi być wypełniony podczas zamknięcia na koniec roku**.

Jeśli ustawisz wartość **Tak**, numer załącznika należy wprowadzić ręcznie podczas procesu zamknięcia na koniec roku. Funkcja numeracji nie jest używana do generowania tego numeru załącznika. Najlepszym rozwiązaniem jest ustawić wartość **Tak**.  

7. Zamknij stronę.
8. Wybierz kolejno opcje **Księga główna > Zamykanie okresu > Zamknięcie na koniec roku**.
9. Kliknij przycisk **Nowy**, aby utworzyć szablon zamknięcia na koniec roku.

Szablon można utworzyć dla grupy firm, dla których ma zostać wykonane zamknięcie na koniec roku. Tego szablonu można używać co rok.  

10. W polu **Nazwa grupy** wprowadź nazwę szablonu zamknięcia na koniec roku.
11. W polu **Kalendarz obrachunkowy** wybierz rok obrachunkowy, dla którego zostanie utworzony szablon.

W szablonie zamknięcia na koniec roku można grupować tylko firmy, które używają tego samego roku obrachunkowego. To dlatego, że zamknięcie na koniec roku wykonuje się przez zaznaczenie roku obrachunkowego, a nie daty.  

12. W **okienku akcji** kliknij pozycję **Zapisz**.
13. W sekcji **osoby prawne** kliknij przycisk **Dodaj**, aby wybrać firmy dla tego szablonu.
    
Firmy mogą być dodawane poprzez wybieranie firm lub wybieranie hierarchii organizacyjnej. Zostaną dodane tylko firmy mające hierarchię organizacyjną z wybranym takim samym kalendarzem obrachunkowym.  

14. Wybierz firmy lub hierarchie organizacyjne.
15. Kliknij przycisk **OK**.
16. Wybierz opcję **Tak** albo **Nie** w **Przenieś wymiary bilansu**.

Jest najlepszym rozwiązaniem, aby ustawić tę opcję na **Tak** dla kont bilansowych. Spowoduje to zachowanie wymiarów finansowych w księgowanych transakcjach podczas tworzenia sald początkowych dla kont bilansowych. Dla kont wynikowych można wybrać opcję zachowania wymiarów finansowych (**Zamknij wszystko**), kiedy salda są przenoszone do dochodów zatrzymanych, lub opcję zastąpienia wymiarów finansowych inną wartością wymiaru (**Zamknij jeden**). Jeśli zostanie wybrana opcja **Zamknij jeden**, można zdefiniować określoną dla każdego wymiaru lub nawet zdecydować się na niewypełnianie tego pola.  

17. Kliknij przycisk **Zapisz**.
18. Uruchom zamknięcia na koniec roku, wybierając operację **Uruchom zamknięcie obrachunkowe** w **Okienku akcji**. Zamknięcia na koniec roku zostanie wykonane dla wybranego szablonu.  
19. W szablonie zaznacz wszystkie lub tylko niektóre firmy, dla których ma zostać wykonane zamknięcie na koniec roku.

Aby podczas pierwszego wykonywania zamknięcia na koniec roku uzyskać salda początkowe, większość organizacji wykonuje zamknięcie na koniec roku dla wszystkich firm zdefiniowanych w szablonie. Jeśli zapisy korygujące zostaną wprowadzone potem, można wykonać zamknięcie na koniec roku tylko dla firm mających korekty.  

20. Kliknij przycisk **OK**.
21. Wybierz rok obrachunkowy, dla którego chcesz wykonać zamknięcie na koniec roku.
22. W **polu Załącznik** wpisz wartość. Jest najlepszym rozwiązaniem, aby uwzględnić rok obrachunkowy w numer załącznika, ponieważ ułatwi do znalezienie utworzonego załącznika zamknięcia na koniec roku.  
23. Zamknięcie na koniec roku domyślnie jest uruchamiane w trybie wsadowym. Dla długotrwałych procesów najlepszym rozwiązaniem jest uruchamianie ich w trybie wsadowym. Zazwyczaj procesy trwają długo, dlatego domyślnie jest używany tryb wsadowy.  
24. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
