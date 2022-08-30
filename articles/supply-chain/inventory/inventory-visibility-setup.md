---
title: Instalowanie dodatku Widoczność magazynu
description: W tym artykule opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 42c2c287e2a813f8bb07ce0c7f21f4224a217946
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306063"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalowanie i konfigurowanie dodatku Inventory Visibility

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.

Musisz korzystać z Microsoft Dynamics Lifecycle Services (LCS), aby zainstalować dodatek Widoczność magazynu. LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Finanse i Działania. Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Zalecamy dołączenie do grupy użytkowników dodatku Widoczność magazynu, gdzie możesz znaleźć przydatne przewodniki, otrzymywać nasze najnowsze aktualizacje oraz zadawać pytania dotyczące korzystania z Widoczności magazynu. Aby dołączyć, wyślij e-mail do zespołu produktu Widoczność magazynu na adres [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) i podaj swój identyfikator środowiska Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Wymagania wstępne dodatku Widoczność magazynu

Aby można było zainstalować dodatek Widoczność magazynu, musisz wykonać następujące zadania:

- Uzyskaj projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.
- Upewnij się, że wymagania wstępne konfigurowania dodatków są spełnione. Więcej informacji o tych wymaganiach wstępnych zawiera temat [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Widoczność zapasów nie wymaga podwójnego łączenia.

> [!NOTE]
> Aktualnie obsługiwane kraje i regiony to Kanada (CCA, ECA), Stany Zjednoczone (WUS, EUS), Unia Europejska (NEU, WEU), Wielka Brytania (SUK, WUK), Australia (EAU, SEAU), Japonia (EJP, WJP) i Brazylia (SBR, SCUS).

Jeśli masz jakiekolwiek pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalowanie dodatku Widoczność magazynu

Przed zainstalowaniem tego dodatku zarejestruj aplikację i dodaj klucz tajny klienta do Azure Active Directory (Azure AD) w swojej subskrypcji Azure. Stosowne instrukcje zawierają tematy [Rejestrowanie aplikacji](/azure/active-directory/develop/quickstart-register-app) i [Dodawanie klucza tajnego klienta](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Pamiętaj o zanotowaniu wartości pól **Identyfikator aplikacji (klienta)**, **Klucz tajny klienta** i **Identyfikator dzierżawy**, ponieważ będą potrzebne później.

> [!IMPORTANT]
> Jeśli masz więcej niż jedno środowisko usługi LCS, utwórz inną aplikację Azure AD dla każdego z nich. Jeśli do zainstalowania dodatku Widoczność magazynu dla różnych środowisk używasz tego samego identyfikatora aplikacji i identyfikatora dzierżawcy, wystąpi problem z tokenem w starszych środowiskach. W związku z tym ważna będzie tylko ostatnia instalacja.

Po zarejestrowaniu aplikacji i dodaniu klucza tajnego klienta do Azure AD wykonaj następujące kroki, aby zainstalować dodatek Widoczność magazynu.

1. Zaloguj się w [LCS](https://lcs.dynamics.com/Logon/Index).
1. Na stronie głównej wybierz projekt, w którym jest wdrożone środowisko.
1. Na stronie projektu wybierz środowisko, w którym chcesz zainstalować dodatek.
1. Przewijaj stronę środowiska w dół do momentu, aż znajdziesz sekcję **Dodatki środowiska** w sekcji **Integracja Power Platform**. Tam znajdziesz nazwę środowiska Dataverse. Potwierdź, że nazwa środowiska Dataverse jest nazwą, której chcesz używać dla widoczności zapasów.

    > [!NOTE]
    > Obecnie są obsługiwane tylko środowiska Dataverse utworzone za pomocą usługi LCS. Jeśli środowisko Dataverse zostało utworzone w inny sposób (na przykład za pomocą centrum administracyjnego Power Apps) i jest połączone ze środowiskiem Supply Chain Management, należy najpierw skontaktować się z zespołem ds. produktu Widoczność magazynu pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com), aby rozwiązać ten problem z mapowaniem. Następnie można zainstalować dodatek Widoczność magazynu.

1. W sekcji **Dodatki środowiska** wybierz opcję **Zainstaluj nowy dodatek**.

    ![Strona środowiska w LCS](media/inventory-visibility-environment.png "Strona środowiska w LCS")

1. Wybierz opcję **Zainstaluj nowy dodatek**. Zostanie otwarta lista dostępnych dodatków.
1. Z listy wybierz opcję **Widoczność magazynu**.
1. Ustaw następujące pola dla swojego środowiska:

    - **Identyfikator aplikacji AAD (klienta)** — wprowadź utworzony i zanotowany wcześniej identyfikator aplikacji Azure AD.
    - **Identyfikator dzierżawy AAD** — wprowadź identyfikator dzierżawy zanotowany wcześniej.

    ![Strona konfiguracji dodatku](media/inventory-visibility-setup.png "Strona konfiguracji dodatku")

1. Zaakceptuj regulamin, zaznaczając pole wyboru **Regulamin**.
1. Wybierz **Zainstaluj**. Stan dodatku będzie widoczny jako **Instalowany**. Po zakończeniu instalacji odśwież stronę. Stan powinien zostać zmieniony na **Zainstalowany**.
1. W Dataverse zaznacz sekcję **Aplikacje** w lewej nawigacji i sprawdź, czy **widoczność zapasów** Power Apps została zainstalowana pomyślnie. Jeśli sekcja **Aplikacje** nie istnieje, skontaktuj się z zespołem ds. produktu Widoczność magazynu pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!NOTE]
> Jeśli instalacja ze strony LCS trwa dłużej niż godzinę, to prawdopodobnie na Twoim koncie użytkownika brakuje uprawnień do instalowania rozwiązań w środowisku Dataverse. Wykonaj następujące czynności, aby rozwiązać problem:
>
> 1. Anuluj proces instalacji dodatku Inventory visibility na stronie LCS.
> 1. Zaloguj się do [centrum administracyjnego Microsoft 365](https://admin.microsoft.com) i upewnij się, że konto użytkownika, którego chcesz używać do zainstalowania tego dodatku, ma przypisaną licencję „Dynamics 365 Unified Operations Plan”. W razie potrzeby przypisz licencję.
> 1. Zaloguj się do [centrum administracyjnego Power Platform,](https://admin.powerplatform.microsoft.com) używając odpowiedniego konta użytkownika. Następnie zainstaluj dodatek Widoczność inwentarza, wykonując następujące czynności:
>     1. Wybierz środowisko, w którym chcesz zainstalować dodatek.
>     1. Wybierz **Aplikacje Dynamics 365**.
>     1. Wybierz **Zainstaluj aplikację**.
>     1. Wybierz **Widoczność magazynu**
>
> 1. Po zakończeniu instalacji wróć na stronę usługi LCS i spróbuj ponownie zainstalować dodatek **Widoczność magazynu**.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Konfigurowanie widoczności zapasów w aplikacji Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Wdróż pakiet integracyjny Widoczność magazynu

Jeśli korzystasz z rozwiązania Supply Chain Management w wersji 10.0.17 lub starszej, skontaktuj się z pokładowym zespołem pomocy technicznej ds. Widoczności zapasów pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com), aby uzyskać paczkę z plikami. Następnie wdróż pakiet w LCS.

> [!NOTE]
> Jeśli podczas wdrażania wystąpi błąd niezgodności wersji, należy ręcznie zaimportować projekt X ++ do środowiska programistycznego. Następnie utwórz pakiet do wdrożenia w swoim środowisku programistycznym i wdróż go w środowisku produkcyjnym.
>
> Kod jest dołączony do programu Supply Chain Management w wersji 10.0.18. Jeśli używasz tej lub nowszej wersji, wdrożenie nie jest wymagane.

Upewnij się, że poniższe funkcje są włączone w środowisku Supply Chain Management. (Domyślnie są włączone).

| Opis funkcji | Wersja kodu | Przełącz klasę |
|---|---|---|
| Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Włączanie lub wyłączanie korzystania z wymiarów magazynowych w tabeli InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Konfiguracja integracji Widoczności zapasów

Po zainstalowaniu tego dodatku należy przygotować system Supply Chain Management do pracy z tym dodatkiem, wykonując następujące kroki.

1. W Supply Chain Management otwórz obszar roboczy **[Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** i włącz następujące funkcje:
    - *Integracja Widoczności zapasów* — wymagana.
    - *Integracja Widoczności zapasów z przesunięciem rezerwacji* — zalecana, ale opcjonalna. Wymaga wersji 10.0.22 lub nowszej. Więcej informacji zawiera temat [Rezerwacje dodatku Widoczność magazynu](inventory-visibility-reservations.md).

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Parametry integracji dodatku Widoczność magazynu**.
1. Otwórz kartę **Ogólne** i wybierz następujące ustawienia:
    - **Punkt końcowy dodatku Widoczność magazynu** — wprowadź adresu URL środowiska, w którym jest uruchamiany dodatek Widoczność magazynu. Więcej informacji można znaleźć w temacie [Znajdowanie punktu końcowego usługi](inventory-visibility-configuration.md#get-service-endpoint).
    - **Maksymalna liczba rekordów w jednym żądaniu** — należy ustawić maksymalną liczbę rekordów, które mają być dołączane w jednym żądaniu. Należy wprowadzić dodatnią liczbę całkowitą mniejszą lub równą 1000. Wartość domyślna to 512. Zdecydowanie zaleca się utrzymywanie wartości domyślnej, chyba że użytkownik otrzyma zawiadomienie od pomocy technicznej firmy Microsoft lub w inny sposób będzie musiał ją zmienić.

1. Jeśli włączono opcjonalną funkcje *Integracja dodatku Widoczność magazynu z przesunięciem rezerwacji*, otwórz kartę **Przesunięcie rezerwacji** i dokonaj następujących ustawień:
    - **Włącz przesunięcie rezerwacji** — aby włączyć tę funkcję, ustaw wartość *Tak*.
    - **Modyfikator przesunięcia rezerwacji** — wybierz stan transakcji magazynowej, który będzie powodować przesunięcie rezerwacji w dodatku Widoczność magazynu. To ustawienie określa etap przetwarzania zamówienia, który wyzwala przesunięcia. Etap jest śledzony według stanu transakcji magazynowej zamówienia. Umożliwia wybranie jednej z poniższych opcji:
        - *Na zamówienie* — w przypadku stanu *W transakcji* po utworzeniu zamówienia będzie wysyłane żądanie przeciwstawne. Ilość przesunięcia będzie ilością z utworzonego zamówienia.
        - *Rezerwa* — w przypadku stanu *Zarezerwuj zamówioną transakcję* zamówienie wysyła żądanie przeciwstawne, gdy zostanie zarezerwowane, skompletowane, zaksięgowane z listą wysyłkową lub zafakturowane. Żądanie zostanie wyzwolone tylko raz, podczas pierwszego kroku w momencie wystąpienia wymienionego procesu. Ilość przesunięcia to ilość, w której stan transakcji magazynowej zmienił się z *Zamówione* na *Zamówione zarezerwowane* (lub późniejszy) w odpowiednim wierszu zamówienia.

1. Przejdź do **Zarządzanie zapasami \> Okresowe \> Integracja widoczności magazynu** i włącz zadanie. Wszystkie zdarzenia zmiany zapasów z Supply Chain Management zostaną teraz zaksięgowane w widoczności magazynu.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Odinstalowywanie dodatku Widoczność magazynu

Aby odinstalować dodatek Widoczność magazynu, trzeba:

1. Zaloguj się do modułu Supply Chain Management.
1. Przejdź do **Zarządzanie zapasami \> Okresowe \> Integracja widoczności magazynu** i wyłącz zadanie.
1. Przejdź do usługi LCS i otwórz stronę środowiska, z którego chcesz odinstalować ten dodatek (zobacz też [Instalowanie dodatku Widoczność zapasów](#install-add-in)).
1. Wybierz **Odinstaluj**.
1. Proces odinstalowywania powoduje teraz zakończenie pracy dodatku Widoczność magazynu oraz wyrejestrowanie dodatku z usługi LCS i usunięcie wszelkich tymczasowych danych przechowywanych w pamięci podręcznej danych dodatku Widoczność magazynu. Jednak podstawowe dane zapasów, które zostały zsynchronizowane w subskrypcji Dataverse, pozostają. Aby usunąć te dane, wykonaj resztę procedury.
1. Otwórz [Power Apps](https://make.powerapps.com).
1. Wybierz **środowisko** na pasku nawigacji
1. Wybierz środowisko Dataverse, które jest połączone ze środowiskiem usługi LCS.
1. Przejdź do obszaru **Rozwiązania** i usuń następujące rozwiązania w następującej kolejności:
    1. Rozwiązanie kotwicy dla aplikacji Inventory Visibility w rozwiązaniach systemu Dynamics 365
    1. Rozwiązanie aplikacji Widoczność magazynu Dynamics 365 FNO SCM
    1. Konfiguracja usługi zapasów
    1. Autonomiczna aplikacja Widoczność magazynu
    1. Rozwiązanie podstawowe Widoczność magazynu Dynamics 365 FNO SCM

    Po usunięciu tych rozwiązań usuwane są także dane przechowywane w tabelach.

> [!NOTE]
> Jeśli baza danych Supply Chain Management zostanie przywrócona po odinstalowaniu dodatku Widoczność zapasów, a następnie użytkownik chce ponownie zainstalować ten dodatek, przed ponownym zainstalowaniem tego dodatku należy upewnić się, że stare dane widoczności zapasów przechowywane w subskrypcji Dataverse (jak opisano w poprzedniej procedurze) zostały usunięte. Pozwoli to uniknąć problemów z niespójnościami danych, które mogłyby wystąpić.

## <a name="clean-inventory-visibility-data-from-dataverse-before-restoring-the-supply-chain-management-database"></a><a name="restore-environment-database"></a>Wyczyść dane widoczności zapasów przed przywróceniem bazy danych Dataverse Supply Chain Management

Jeśli użytkownik używa widoczności zapasów, a następnie przywraca bazę danych Supply Chain Management, przywrócona baza danych może zawierać dane, które nie są spójne z danymi poprzednio zsynchronizowanymi przez widoczność zapasów do Dataverse. Ta niespójność danych może spowodować błędy systemowe i inne problemy. Dlatego przed przywróceniem bazy danych Supply Chain Management ważne jest, aby przed przywróceniem bazy wyczyścić wszystkie dane dotyczące widoczności zapasów z Dataverse.

Aby przywrócić bazę danych Supply Chain Management, należy skorzystać z następującej procedury:

1. Odinstaluj dodatek Widoczność zapasów i usuń wszystkie powiązane dane w Dataverse, jak opisano w [Odinstaluj dodatek Widoczność zapasów](#uninstall-add-in)
1. Przywróć bazę danych Supply Chain Management, na przykład w sposób opisany w części [Przywracanie punktu w czasie bazy danych (PITR)](../../fin-ops-core/dev-itpro/database/database-point-in-time-restore.md) lub [przywracanie bazy danych produkcji na raz do środowiska piaskownicy](../../fin-ops-core/dev-itpro/database/database-pitr-prod-sandbox.md).
1. Aby nadal korzystać z tej funkcji, zainstaluj ponownie i skonfiguruj dodatek Widoczność zapasów w sposób opisany w te sposób: [Zainstaluj dodatek widoczność zapasów](#install-add-in) oraz [skonfiguruj integrację z widocznością zapasów](#setup-inventory-visibility-integration)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
