---
title: Instalowanie dodatku Widoczność magazynu
description: W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a49f35211f30cdb76104cc5be78f5b114320a228
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062657"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalowanie i konfigurowanie dodatku Widoczność magazynu

[!include [banner](../includes/banner.md)]


W tym temacie opisano sposób instalowania i konfigurowania dodatku Widoczność magazynu dla systemu Microsoft Dynamics 365 Supply Chain Management.

Musisz korzystać z Microsoft Dynamics Lifecycle Services (LCS), aby zainstalować dodatek Widoczność magazynu. LCS to portal współpracy, który zapewnia środowisko i zbiór regularnie zaktualizowanych usług ułatwiających zarządzanie cyklem życia aplikacji w aplikacjach Finanse i Działania.

Aby uzyskać więcej informacji, zobacz [Zasoby w Lifecycle Services (LCS)](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Wymagania wstępne dodatku Widoczność magazynu

Aby można było zainstalować dodatek Widoczność magazynu, musisz wykonać następujące zadania:

- Uzyskaj projekt implementacji usługi LCS z co najmniej jednym wdrożonym środowiskiem.
- Upewnij się, że wymagania wstępne konfigurowania dodatków są spełnione. Więcej informacji o tych wymaganiach wstępnych zawiera temat [Omówienie dodatków](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Widoczność zapasów nie wymaga podwójnego łączenia.

> [!NOTE]
> Aktualnie obsługiwane kraje i regiony to Kanada (CCA, ECA), Stany Zjednoczone (WUS, EUS), Unia Europejska (NEU, WEU), Wielka Brytania (SUK, WUK), Australia (EAU, SEAU), Japonia (EJP, WJP) i Brazylia (SBR, SCUS).

Jeśli masz jakiekolwiek pytania dotyczące tych wymagań wstępnych, skontaktuj się z zespołem ds. produktu Widoczność magazynu pod adresem [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalowanie dodatku Widoczność magazynu

Przed zainstalowaniem tego dodatku zarejestruj aplikację i dodaj klucz tajny klienta do Azure Active Directory (Azure AD) w swojej subskrypcji Azure. Stosowne instrukcje zawierają tematy [Rejestrowanie aplikacji](/azure/active-directory/develop/quickstart-register-app) i [Dodawanie klucza tajnego klienta](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Pamiętaj o zanotowaniu wartości pól **Identyfikator aplikacji (klienta)**, **Klucz tajny klienta** i **Identyfikator dzierżawy**, ponieważ będą potrzebne później.

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

> [!TIP]
> Zalecamy dołączenie do grupy użytkowników dodatku Widoczność magazynu, gdzie możesz znaleźć przydatne przewodniki, otrzymywać nasze najnowsze aktualizacje oraz zadawać pytania dotyczące korzystania z Widoczności magazynu. Aby dołączyć, wyślij e-mail do zespołu produktu Widoczność magazynu na adres [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) i podaj swój identyfikator środowiska Supply Chain Management.

> [!IMPORTANT]
> Jeśli masz więcej niż jedno środowisko usługi LCS, utwórz inną aplikację Azure AD dla każdego środowiska. Jeśli do zainstalowania dodatku Widoczność magazynu dla różnych środowisk używasz tego samego identyfikatora aplikacji i identyfikatora dzierżawcy, wystąpi problem z tokenem w starszych środowiskach. Tylko ostatnie zainstalowane rozwiązanie jest prawidłowe.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Odinstalowywanie dodatku Widoczność magazynu

Aby odinstalować dodatek Widoczność magazynu, wybierz opcję **Odinstaluj** na stronie usługi LCS. Proces odinstalowywania powoduje zakończenie pracy dodatku Widoczność magazynu oraz wyrejestrowanie dodatku z usługi LCS i usunięcie wszelkich tymczasowych danych przechowywanych w pamięci podręcznej danych dodatku Widoczność magazynu. Jednak podstawowe dane zapasów przechowywane w subskrypcji Dataverse nie są usuwane.

Aby odinstalować dane magazynu przechowywane w subskrypcji Dataverse, otwórz [Power Apps](https://make.powerapps.com), wybierz pozycję **Środowisko** na pasku nawigacyjnym i wybierz środowisko Dataverse, które jest połączone ze środowiskiem usługi LCS. Następnie przejdź do obszaru **Rozwiązania** i usuń następujące pięć rozwiązań w tej kolejności:

1. Zakotwiczone rozwiązanie aplikacji Widoczność magazynu w rozwiązaniach Dynamics 365
1. Rozwiązanie aplikacji Widoczność magazynu Dynamics 365 FNO SCM
1. Konfiguracja usługi zapasów
1. Autonomiczna aplikacja Widoczność magazynu
1. Rozwiązanie podstawowe Widoczność magazynu Dynamics 365 FNO SCM

Po usunięciu tych rozwiązań usuwane są także dane przechowywane w tabelach.

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
    - **Modyfikator przesunięcia rezerwacji** — wybierz stan transakcji magazynowej, który będzie powodować przesunięcie rezerwacji w dodatku Widoczność magazynu. To ustawienie określa etap przetwarzania zamówienia, który wyzwala przesunięcia. Etap jest śledzony według stanu transakcji magazynowej zamówienia. Wybierz jedną z następujących opcji:
        - *Na zamówienie* — w przypadku stanu *W transakcji* po utworzeniu zamówienia będzie wysyłane żądanie przeciwstawne. Ilość przesunięcia będzie ilością z utworzonego zamówienia.
        - *Rezerwa* — w przypadku stanu *Zarezerwuj zamówioną transakcję* zamówienie wysyła żądanie przeciwstawne, gdy zostanie zarezerwowane, skompletowane, zaksięgowane z listą wysyłkową lub zafakturowane. Żądanie zostanie wyzwolone tylko raz, podczas pierwszego kroku w momencie wystąpienia wymienionego procesu. Ilość przesunięcia to ilość, w której stan transakcji magazynowej zmienił się z *Zamówione* na *Zamówione zarezerwowane* (lub późniejszy) w odpowiednim wierszu zamówienia.

1. Przejdź do **Zarządzanie zapasami \> Okresowe \> Integracja widoczności magazynu** i włącz zadanie. Wszystkie zdarzenia zmiany zapasów z Supply Chain Management zostaną teraz zaksięgowane w widoczności magazynu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
