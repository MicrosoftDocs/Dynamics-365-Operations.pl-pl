Podczas kopiowania bazy danych między środowiskami musisz uruchomić narzędzie do ponownego inicjowania obsługi środowiska, zanim skopiowana baza danych osiągnie pełną funkcjonalność, aby zagwarantować aktualność wszystkich składników rozwiązania Retail.

> [!IMPORTANT]
> Zalecamy wykonanie tej procedury niezależnie od tego, czy używasz składników rozwiązania Retail, czy nie, ponieważ funkcjonalność rozwiązania Retail wchodzi w skład wszystkich środowisk. 

Przed kontynuowaniem upewnij się, że są spełnione następujące wymagania wstępne:
1. Jeśli wykonujesz uaktualnienie do wydania z lipca 2017 (znanego też pod numerem 7.2) 7.2.11792.56024, zastosuj wymienione poniżej poprawki kodu aplikacji w języku X++ w środowisku docelowym, zanim rozpoczniesz uaktualnianie danych w tym środowisku. Zapobiegnie to wystąpieniu różnych błędów podczas uaktualniania danych:

    - KB 4036156 — Uaktualnienie wersji pomocniczej rozwiązania Retail — „Nie ustawiono sekwencji numerów wariantu.” Ten pakiet poprawek zawiera także poprawki KB 4035399 i KB 4035751. Pamiętaj, że aby móc użyć tego pakietu, musisz mieć co najmniej aktualizację Platform Update 9. Jeśli nie masz pewności, zainstaluj najnowsze pliki binarne.
    
2. Jeśli wykonujesz uaktualnienie z wersji Microsoft Dynamics AX 2012, zainstaluj wymienione poniżej poprawki kodu aplikacji w języku X++ w środowisku docelowym, zanim rozpoczniesz uaktualnianie danych:
    - KB 4033183 — Uaktualnianie systemu Dynamics AX 2012 R2 lub Dynamics AX 2012 R3 Pre-CU8 w wersji innej niż detaliczna kończy się niepowodzeniem z powodu błędu Nie znaleziono obiektu dotyczącego pliku dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 — Uaktualnianie systemu Dynamics AX 2012 R3 do rozwiązania Microsoft Dynamics 365 for Operations 7.2 kończy się niepowodzeniem z powodu zduplikowanego indeksu RetailSalesLine w tabeli SalesLineIdx.
    - KB 4035490 — Problem z wydajnością skryptu uaktualniania pola MainAccount w tabeli GeneralJournalAccountEntry.


Wykonaj poniższe kroki, aby uruchomić narzędzie do ponownego inicjowania obsługi środowiska.

1. W bibliotece udostępnionych elementów zawartości wybierz pozycję **Wdrażalny pakiet oprogramowania**.
2. Pobierz narzędzie do ponownego inicjowania obsługi środowiska.
3. W bibliotece elementów zawartości swojego projektu wybierz pozycję **Wdrażalny pakiet oprogramowania**.
4. Wybierz pozycję **Nowy**, aby utworzyć nowy pakiet.
5. Wprowadź nazwę i opis pakietu. Jako nazwy pakietu możesz użyć ciągu **Narzędzie do ponownego inicjowania obsługi środowiska**.
6. Przekaż pobrany wcześniej pakiet.
7. Na stronie **Szczegóły środowiska** dotyczącej Twojego środowiska docelowego wybierz kolejno pozycje **Konwersacja** > **Zastosuj aktualizacje**.
8. Wybierz narzędzie do ponownego inicjowania obsługi środowiska, które zostało przekazane wcześniej, a następnie wybierz pozycję **Zastosuj**, aby zastosować pakiet.
9. Monitoruj postęp wdrażania pakietu. 

Aby uzyskać więcej informacji dotyczących sposobu stosowania wdrażalnego pakietu, zobacz [Stosowanie wdrażalnego pakietu](../deployment/create-apply-deployable-package.md). Aby uzyskać więcej informacji dotyczących sposobu ręcznego stosowania wdrażalnego pakietu, zobacz [Instalowanie wdrażalnego pakietu](../deployment/install-deployable-package.md).
