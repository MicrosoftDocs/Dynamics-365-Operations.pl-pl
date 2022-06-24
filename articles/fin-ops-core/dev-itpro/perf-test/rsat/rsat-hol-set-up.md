---
title: Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool
description: Ten artykuł zawiera Samouczek przedstawiający sposób konfigurowania i instalowania narzędzia Regression Suite Automation Tool (RSAT).
author: tonyafehr
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: ec4ae765aaac038e6c7eff11403fb21ebd27fc2c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858598"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Konfigurowanie i instalowanie samouczka narzędzia Regression Suite Automation Tool

Ten artykuł jest samouczkiem, który pomaga w konfigurowaniu systemu i rozpoczynaniu pracy z narzędziem RSAT oraz innymi narzędziami związanymi z korzystaniem z niego.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Tę stronę można pobrać i zapisać w formacie PDF przy użyciu narzędzi dostępnych w przeglądarce internetowej.

## <a name="key-concepts"></a>Podstawowe pojęcia

- Opis instalacji i wymagań wstępnych, które są wymagane w przypadku różnych aplikacji obsługujących narzędzie Regression Suite Automation Tool (RSAT).
- Sposób, w jaki funkcja Rejestrator zadań w rozwiązaniu Microsoft Dynamics wraz z usługą Lifecycle Services (LCS) i usługą Microsoft Azure DevOps, umożliwia tworzenie, konfigurowanie, uruchamianie, badanie i raportowanie przypadków testowych.
- Umożliwienie użytkownikom rejestrowania zadań biznesowych za pomocą rejestratora zadań, a następnie konwertowania nagrań zadania na pakiet automatycznych testów bez konieczności pisania kodu źródłowego.

## <a name="before-you-begin"></a>Przed rozpoczęciem

### <a name="prerequisites"></a>Wymagania wstępne

- W tym samouczku jest wymagane środowisko rozwiązania Microsoft Dynamics 365 for Finance and Operations w wersji 10.0 (kwiecień 2019) lub nowszej. W przypadku klientów korzystających z rozwiązania Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3, obsługiwana jest także aktualizacja Platform update 20 (PU20) lub nowsza.
- Użytkownik musi mieć uprawnienia administratora do tego środowiska.
- Użytkownik musi mieć dostęp do dzierżawy klienta usługi LCS oraz usługi Azure DevOps (znanej wcześniej jako Microsoft Visual Studio Team Services \[VSTS\]).
- Użytkownik, który tworzy pakiety testów i zarządza nimi, musi mieć licencję Plany testów lub Menedżer testów do usługi Azure DevOps. Następujące licencje również umożliwiają dostęp do planów testów:
    - Licencja Visual Studio Enterprise
    - Licencja Visual Studio Test Professional
    - Licencja subskrybenta platform MSDN
- Narzędzie RSAT musi mieć dostęp do środowiska testowego za pośrednictwem przeglądarki sieci web.
- Aby generować i edytować parametry testowe, należy mieć zainstalowany program Microsoft Excel.

## <a name="configure-azure-devops"></a>Konfigurowanie usługi Azure DevOps

### <a name="user-eligibility"></a>Uprawnienia użytkownika

Użytkownik musi być utworzony w usłudze Azure DevOps i mieć poziom subskrypcji zapewniający dostęp do planów testów usługi Azure. Licencja Plany testów usługi Azure DevOps jest wymagana tylko wtedy, gdy użytkownik tworzy przypadki testowe i zarządza nimi (czyli nie każdy użytkownik narzędzia RSAT musi mieć tę licencję). Aby uzyskać informacje dotyczące wymagań dotyczących licencji, zapoznaj się z [wymaganiami dotyczącymi licencji](/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Tworzenie nowego projektu w usłudze Azure DevOps

W narzędziu RSAT do zarządzania przypadkami testowymi i pakietami testów, raportowania ich i analizowania wyników przebiegu testowego jest wykorzystywana usługa Azure DevOps.

> [!NOTE]
> Użycie istniejącego projektu usługi Azure DevOps jest możliwe. Jeśli jednak istniejący projekt usługi Azure DevOps jest skonfigurowany w taki sposób, że zawiera szablon niestandardowy, podczas synchronizowania przypadków testowych z narzędziem do modelowania procesów biznesowych (BPM) zostanie wyświetlony komunikat o błędzie „Niepowodzenie synchronizacji usługi VSTS” Azure DevOps (zobacz sekcję [Testowanie synchronizacji między narzędziem BPM a usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Jeśli szablon niestandardowy został wykonany zgodnie z następującymi najlepszymi praktykami, będzie możliwe zsynchronizowanie przypadków testowych z usługą Azure DevOps. (Te najlepsze praktyki są wymienione w komunikacie o błędzie).

- Nie usuwaj żadnych typów elementów roboczych ani standardowych pól.
- Nie usuwaj żadnego stanu typu elementu roboczego.
- Nie dodawaj żadnych wymaganych pól do typu elementu roboczego.

![Komunikat o błędzie z listą najlepszych praktyk.](./media/setup_rsa_tool_02.png)

W przeciwnym razie zaleca się utworzenie nowego projektu Azure DevOps i korzystanie z niego w trakcie tego samouczka. Aby uzyskać więcej informacji, zobacz temat [Problemy występujące podczas synchronizacji z narzędziem BPM przy użyciu niestandardowego szablonu procesu usługi Azure DevOps (VSTS)](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Otwórz adres URL usługi Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).
2. Kliknij przycisk **Utwórz projekt** w prawym górnym rogu strony usługi Azure DevOps.

    ![Przycisk Utwórz projekt.](./media/setup_rsa_tool_03.png)

3. Wypełnij następujące pola, a następnie kliknij przycisk **Utwórz**:

    - **Nazwa projektu**
    - **Kontrola wersji** — wybierz opcję **Kontrola wersji serwera Team Foundation**. Domyślna opcja, **Git**, nie jest obsługiwana.
    - **Proces elementu roboczego**

    ![Okno dialogowe Tworzenie nowego projektu.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Tworzenie osobistego tokenu dostępu

W tym samouczku utworzysz bibliotekę przypadków testowych i zsynchronizujesz przypadki testowe z usługą Azure DevOps przy użyciu narzędzia do modelowania procesów biznesowych (BPM) usługi LCS. Do synchronizacji narzędzia BPM z usługą Azure DevOps będzie potrzebny osobisty token dostępu.

1. Kliknij ikonę profilu w prawym górnym rogu strony usługi Azure DevOps projektu, a następnie kliknij przycisk **Zabezpieczenia**.

    ![Polecenie Zabezpieczenia.](./media/setup_rsa_tool_05.png)

2. W lewym okienku, w sekcji **Zabezpieczenia** kliknij przycisk **Osobiste tokeny dostępu**. Następnie kliknij przycisk **Nowy token**.

    ![Przycisk Nowy token na karcie Osobiste tokeny dostępu w oknie Ustawienia użytkownika.](./media/setup_rsa_tool_06.png)

3. Wypełnij następujące pola, a następnie kliknij przycisk **Utwórz**:

    - **Imię i nazwisko**
    - **Wygaśnięcie (UTC)** — kliknij przycisk **Niestandardowe**, a następnie wybierz najpóźniejszą dostępną datę w selektorze daty.
    - **Zakresy** — wybierz opcję **Pełny dostęp**.

    ![Okno dialogowe Tworzenie nowego osobistego tokenu dostępu.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Zanotuj osobisty token dostępu, który został utworzony. Będzie on potrzebny w późniejszym czasie podczas konfigurowania narzędzia RSAT.

    ![Osobisty token dostępu.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Konfigurowanie projektu w usłudze LCS

Potrzebujesz projektu w usłudze Lifecycle Services (LCS) na główną bibliotekę testów. Główna biblioteka przypadków testowych będzie zarządzana za pomocą narzędzia do modelowania procesów biznesowych usługi LCS (BPM). Narzędzie BPM służy do zarządzania bibliotekami testów i dystrybuowania ich w projektach usługi LCS. Na przykład partner firmy Microsoft lub niezależny dostawca oprogramowania (ISV) tworzyć biblioteki testów będzie publikował przypadki testowe w formie bibliotek narzędzia BPM. W narzędziu BPM przypadki testowe są zorganizowane według procesu biznesowego. Narzędzie BPM nie wyznacza kolejności wykonywania ani częstotliwości przebiegu testowego. Te szczegóły są określane w usłudze Azure DevOps w sposób opisany w dalszej części tego artykułu.  

Jako projektu usługi LCS można użyć istniejącej implementacji klienta lub projektu partnera.

### <a name="update-the-lcs-language"></a>Aktualizowanie języka usługi LCS

> [!NOTE]
> Aby procesy biznesowe były poprawnie wyświetlane w interfejsie użytkownika, jako preferowany język usługi LCS musi być wybrany **angielski (Stany Zjednoczone)**.

1. Przejdź do projektu implementacji usługi LCS.
2. Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu strony, a następnie kliknij przycisk **Preferencje języka**.

    ![Zaktualizuj preferencje dotyczące języka.](./media/setup_rsa_tool_09.png)

3. W polu **Preferowany język** wybierz opcję **angielski (Stany Zjednoczone)**, a następnie kliknij przycisk **Zapisz**.

    ![Karta Preferencje języka w oknie Ustawienia użytkownika.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Konfigurowanie połączenia z projektem usługi Azure DevOps w usłudze LCS

Jeśli wcześniej utworzono nowy projekt usługi Azure DevOps, skonfiguruj połączenie z tym projektem w projekcie usługi LCS. Jeśli projekt usługi LCS jest już połączony z projektem usługi Azure DevOps, możesz przejść do następnej sekcji.

1. Przejdź do projektu implementacji usługi LCS.
2. Kliknij przycisk **Menu**, a następnie kliknij przycisk **Ustawienia projektu**.

    ![Polecenie Ustawienia projektu.](./media/setup_rsa_tool_11.png)

3. W lewym okienku kliknij przycisk **Visual Studio Team Services**, a następnie kliknij przycisk **Ustawienia usługi Visual Studio Team Services**.

    ![Karta Ustawienia usługi Visual Studio Team Services w oknie Ustawienia projektu.](./media/setup_rsa_tool_12.png)

4. W polu **Adres URL witryny usługi Azure DevOps** wpisz adres URL witryny usługi Azure DevOps. W polu **Osobisty token dostępu** wpisz osobisty token dostępu, który został utworzony wcześniej.

    > [!NOTE]
    > Chociaż usługa VSTS obecnie jest znana jako Azure DevOps, w celu połączenia usługi LCS z projektem Azure DevOps użyj starego adresu URL. Na przykład adres URL usługi Azure DevOps używany w tym samouczku to `https://dev.azure.com/D365FOFastTrack/`. Jednak na poniższej ilustracji jest on wprowadzony jako `https://D365FOFastTrack.visualstudio.com/`.

    ![Krok 1 w oknie Konfigurowanie usługi Visual Studio Team Services.](./media/setup_rsa_tool_13.png)

5. Kliknij przycisk **Kontynuuj**.
6. W polu **Projekt usługi Visual Studio Team Services** wybierz projekt usługi VSTS w wybranej witrynie, aby połączyć go z projektem usługi LCS. Domyślne ustawienie w polu **Szablon procesu** to wartość **Zwinne wytwarzanie oprogramowania**. W przypadku szablonu niestandardowego należy zapoznać się ze najlepszymi praktykami podanymi w sekcji [Tworzenie nowego projektu w usłudze Azure DevOps](#create-a-new-azure-devops-project). Następnie kliknij przycisk **Kontynuuj**.

    ![Krok 2 w oknie Konfigurowanie usługi Visual Studio Team Services.](./media/setup_rsa_tool_14.png)

7. Przejrzyj ustawienia, a następnie kliknij przycisk **Zapisz**.

    ![Krok 3 w oknie Konfigurowanie usługi Visual Studio Team Services.](./media/setup_rsa_tool_15.png)

8. Kliknij przycisk **Autoryzuj**, aby autoryzować dostęp usługi LCS do skonfigurowanej witryny usługi Azure DevOps w swoim imieniu i włączyć funkcje integrowania z usługą VSTS.

    ![Przycisk Autoryzuj.](./media/setup_rsa_tool_16.png)

9. Zostanie wyświetlony następujący komunikat: „Nastąpi przekierowanie do witryny zewnętrznej w celu autoryzacji usługi LCS do nawiązywania połączenia z usługą Visual Studio Team Services w Twoim imieniu. Kontynuować?” Wybierz opcję **Tak**.

    ![Okno komunikatu.](./media/setup_rsa_tool_17.png)

10. Wybierz **Akceptuj**.

    ![Autoryzowanie dostępu.](./media/setup_rsa_tool_18.png)

11. Jeśli jesteś autoryzowanym użytkownikiem, w interfejsie użytkownika powinna zostać ponownie wyświetlona strona Ustawienia projektu usługi LCS.

    ![Autoryzowany użytkownik.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Tworzenie nowej biblioteki BPM

1. Przejdź do projektu implementacji usługi LCS.
2. Kliknij przycisk **Menu**, a następnie kliknij przycisk **Narzędzie do modelowania procesów biznesowych**.

    ![Polecenie Narzędzie do modelowania procesów biznesowych.](./media/setup_rsa_tool_20.png)

3. Kliknij przycisk **Nowa biblioteka**.

    ![Przycisk Nowa biblioteka.](./media/setup_rsa_tool_21.png)

4. W polu **Nazwa biblioteki** wprowadź nazwę, a następnie kliknij przycisk **Utwórz**. W tym samouczku nazwij bibliotekę narzędzia BPM **RSAT**.

    ![Okno dialogowe Tworzenie nowej biblioteki.](./media/setup_rsa_tool_22.png)

5. Otwórz nową bibliotekę narzędzia BPM **RSAT**.
6. Wybierz proces **Przykładowy podstawowy proces biznesowy**, a następnie kliknij przycisk **Tryb edycji** po prawej stronie.

    ![Przycisk Tryb edycji.](./media/setup_rsa_tool_23.png)

7. Zmień wartość w polach **Nazwa** i **Opis** na **Tworzenie produktu**. Następnie kliknij przycisk **Zapisz**.

    ![Pola Nazwa i Opis.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Środowisko

### <a name="version-requirement"></a>Wymaganie dotyczące wersji

Wymagane jest środowisko testowe lub piaskownicy w wersji 10. W przypadku klientów korzystających z wersji 7.3 obsługiwana jest także aktualizacja Platform update 20 lub nowsza.

> [!NOTE]
> Narzędzie RSAT musi mieć dostęp do środowiska testowego za pośrednictwem przeglądarki sieci web.

### <a name="user-criteria"></a>Kryteria użytkownika

Użytkownik musi mieć uprawnienia administratora do tego środowiska.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Konfigurowanie ustawień Pomocy w celu nawiązania połączenia z usługą LCS

Ten krok jest wymagany w celu nawiązania połączenia z usługi LCS, aby nagrania zadania mogły być zapisywane w odpowiedniej bibliotece narzędzia BPM w usłudze LCS za pośrednictwem klienta.

1. Otwórz klienta.
2. Wybierz kolejno opcje **Administrowanie systemem \> Ustawienia \> Parametry systemu**.
3. Na karcie **Pomoc**, w polu **Konfiguracja pomocy usługi Lifecycle Services** wybierz odpowiedni projekt usługi LCS (**RSAT** w tym samouczku).

    ![Pole Konfiguracja pomocy usługi Lifecycle Services na karcie Pomoc.](./media/setup_rsa_tool_25.png)

    Biblioteki narzędzia BPM zostaną wypełnione w odpowiednim projekcie usługi LCS.

4. Wybierz opcję **Zapisz**.
5. W celu wyświetlenia zaktualizowanej zawartości pomocy może być konieczne odświeżenie przeglądarki.

    ![Powiadomienie o odświeżeniu przeglądarki.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Nagrania zadania

> [!NOTE]
> Wszystkie nagrania zadania muszą być rozpoczynane na głównym pulpicie nawigacyjnym. Poszczególne nagrania powinny być krótkie i dotyczyć konkretnego zadania biznesowego, jak tworzenie zamówienia sprzedaży.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM

Utwórz odpowiednie nagranie zadania, które można dołączyć do prostego procesu biznesowego utworzonego w nowej bibliotece narzędzia BPM.

1. Otwórz klienta.
2. Na głównym pulpicie nawigacyjnym kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Rejestrator zadań**.

    ![Wybierz Rejestrator zadań w menu Ustawienia.](./media/setup_rsa_tool_27.png)

3. Kliknij przycisk **Utwórz nagranie**.

    ![Przycisk Utwórz nagranie.](./media/setup_rsa_tool_28.png)

4. Wypełnij pola **Nazwa nagrania** i **Opis nagrania**, a następnie kliknij przycisk **Rozpocznij**.

    ![Pola Nazwa nagrania i Opis nagrania.](./media/setup_rsa_tool_29.png)

5. Zarejestruj kroki tworzenia produktu. Po zakończeniu kliknij przycisk **Zatrzymaj**, aby zatrzymać rejestrowanie.

    ![Kroki tworzenia produktu.](./media/setup_rsa_tool_30.png)

6. Kliknij przycisk **Zapisz w usłudze Lifecycle Services**.

    ![Zapisz nagranie zadania w usługach Lifecycle Services.](./media/setup_rsa_tool_31.png)

    Informacje o bibliotece zostaną załadowane z usługi LCS.

    ![Ładowanie informacji o bibliotece.](./media/setup_rsa_tool_32.png)

7. Wybierz bibliotekę narzędzia BPM do skojarzenia z nagraniem zadania. W tym samouczku wybierz bibliotekę **RSAT** narzędzia BPM, która została utworzona wcześniej, oraz należący do niej proces biznesowy **Tworzenie produktu**. Następnie wybierz opcję **OK**.

    ![Kojarzenie nagrania zadania z biblioteką narzędzia BPM i procesem biznesowym.](./media/setup_rsa_tool_33.png)

    Zostanie wyświetlony komunikat „Zapisywanie w usłudze Lifecycle Services zakończyło się pomyślnie”.

    ![Komunikat o pomyślnym zapisaniu w usłudze LCS.](./media/setup_rsa_tool_34.png)

8. Jeśli chcesz zapisać lokalnie nagranie zadania, a następnie przekazać je do narzędzia BPM za pośrednictwem usługi LCS, wykonaj następujące kroki:

    1. Po zakończeniu rejestrowania kliknij przycisk **Zapisz na tym komputerze**.

        ![Zapisz na tym komputerze.](./media/setup_rsa_tool_35.png)

    2. Na pasku powiadomień przeglądarki kliknij przycisk **Zapisz** lub **Zapisz jako,** aby zapisać plik na komputerze lokalnym.

        ![Pasek powiadomień.](./media/setup_rsa_tool_36.png)

    3. Przejdź do biblioteki **RSAT** narzędzia BPM i wybierz proces biznesowy, którego nagranie zadania ma zostać zapisane.
    4. Na karcie **Przegląd** kliknij przycisk **Przekaż**.

        ![Przycisk Przekaż.](./media/setup_rsa_tool_37.png)

    5. Kliknij przycisk **Przeglądaj**, a następnie zaznacz plik axtr, który został wcześniej zapisany. Następnie kliknij przycisk **Przekaż**.

        ![Wybieranie pliku axtr do przekazania.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps

Po dołączeniu nagrania zadania do procesu biznesowego należy sprawdzić, czy proces biznesowy może być synchronizowany z usługą Azure DevOps jako funkcją, a skojarzone z nim nagranie zadania z przypadkiem testowym przy użyciu funkcji synchronizacji usługi VSTS w usłudze LCS.

> [!NOTE]
> Odpowiedni typ elementu roboczego, który jest tworzony w usłudze Azure DevOps, zależy od szablonu procesu wybranego podczas konfigurowania projektu usługi LCS za pomocą usługi Azure DevOps, zgodnie z opisem w sekcji [Tworzenie nowego projektu usługi Azure DevOps](#create-a-new-azure-devops-project).

1. Przejdź do biblioteki narzędzia BPM i otwórz utworzoną wcześniej bibliotekę **RSAT**.
2. Kliknij przycisk wielokropka(**...**) i wybierz polecenie **Synchronizacja z usługą VSTS**.

    ![Polecenie Synchronizacja z usługą VSTS w menu wielokropka.](./media/setup_rsa_tool_39.png)

    Po zakończeniu synchronizacji z usługą VSTGS po lewej stronie zostanie wyświetlona karta **Wymagania**, która zawiera odpowiedni element roboczy usługi Azure DevOps.

    > [!NOTE]
    > Prefiksem tytułu elementu roboczego utworzonego w usłudze Azure DevOps będzie nazwa biblioteki narzędzia BPM.

    ![Karta Wymagania.](./media/setup_rsa_tool_40.png)

3. Odśwież stronę.
4. Kliknij przycisk wielokropka(**...**). Zostanie wyświetlona dodatkowa opcja, **Synchronizuj przypadki testowe**. Wybierz tę opcję.

    ![Polecenie Synchronizuj przypadki testowe w menu wielokropka.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Jeśli po odświeżeniu strony opcja **Synchronizuj przypadki testowe** nie jest dostępna, przejdź do strony głównej narzędzia BPM i kliknij przycisk **Synchronizuj przypadki testowe** na poziomie całej biblioteki. W ten sposób wymusisz synchronizację całej biblioteki.
    >
    > ![Klikanie przycisku Synchronizuj przypadki testowe na poziomie całej biblioteki.](./media/setup_rsa_tool_42.png)

    Po zakończeniu synchronizacji przypadków testowych na karcie **Wymagania** zostanie utworzony nowy przypadek testowy.

    ![Nowy przypadek testowy na karcie Wymagania.](./media/setup_rsa_tool_43.png)

5. Przejdź do projektu usługi Azure DevOps i wybierz opcje **Tablice \> Elementy robocze**.

    ![Polecenie Elementy robocze w menu Tablice.](./media/setup_rsa_tool_44.png)

6. Sprawdź, czy istnieje element roboczy i przypadek testowy utworzony w trakcie synchronizacji narzędzia BPM.

    ![Element roboczy i przypadek testowy.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Instalowanie i konfigurowanie narzędzia RSAT

Narzędzie RSAT można zainstalować na dowolnym komputerze z systemem Windows 10, na którym można z poziomu przeglądarki internetowej (Internet Explorer lub Google Chrome) otworzyć środowisko.

> [!NOTE]
> Przed zainstalowaniem nowej wersji narzędzia zaleca się odinstalowanie poprzedniej wersji.

### <a name="install-an-authentication-certificate"></a>Instalowanie certyfikatu uwierzytelniania

Aby włączyć uwierzytelnianie, należy wygenerować i zainstalować certyfikat na tym samym komputerze, na którym uruchomione jest narzędzie RSAT.

#### <a name="generate-a-certificate"></a>Generowanie certyfikatu

1. Aby wygenerować plik certyfikatu, otwórz okno środowiska Microsoft Windows PowerShell jako administrator i uruchom następujące polecenie.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Otwórz Menedżera certyfikatów, wpisując nazwę **certlm.msc** w oknie dialogowym **Uruchamianie**, i sprawdź, czy certyfikat **D365 Automated testing certificate** został utworzony w sekcji **Osobiste \> Certyfikaty**.

    > [!NOTE]
    > Uważaj, aby wpisać **certlm.msc**, a nie **certmgr.msc**, ponieważ certyfikaty są przechowywane na komputerze lokalnym.

    ![Certyfikat D365 Automated testing certificate.](./media/setup_rsa_tool_46.png)

3. Kliknij prawym przyciskiem myszy certyfikat, a następnie wybierz polecenie **Kopiuj**.
4. Wybierz kolejno opcje **Zaufane główne urzędy certyfikacji \> Certyfikaty**.

    ![Folder Certyfikaty w folderze Zaufane główne urzędy certyfikacji.](./media/setup_rsa_tool_47.png)

5. W menu **Akcja** wybierz polecenie **wklej**, aby skopiować certyfikat do lokalizacji **Zaufane główne urzędy certyfikacji**.

    ![Polecenie Wklej w menu Akcja.](./media/setup_rsa_tool_48.png)

6. Aby uzyskać odcisk palca zainstalowanego certyfikatu, ale bez spacji i znaków specjalnych, otwórz okno środowiska Windows PowerShell jako administrator i uruchom następujące polecenia.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Zapisz odcisk palca, ponieważ będzie on potrzebny później, gdy zaktualizujesz pliki.WIF dla serwera obiektów aplikacji (AOS) i skonfigurujesz narzędzie RSAT.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Konfigurowanie zaufanego połączenia na komputerze AOS

> [!NOTE]
> Jeśli środowisko jest środowiskiem warstwy 2 lub wyższej, odcisk palca certyfikatu musi zostać zaktualizowany w pliku wif.config dla **wszystkich** komputerów AOS środowiska.

1. Ustanów połączenie protokołu RDP (Remote Desktop Protocol) z komputerem AOS. Szczegóły logowania są dostępne na stronie szczegółów środowiska w usłudze LCS.
2. Otwórz program Microsoft Internet Information Services (IIS) i znajdź pozycję **AOSService** na liście witryn.

    ![AOSService na liście witryn.](./media/setup_rsa_tool_49.png)

3. Kliknij prawym przyciskiem myszy polecenie **Eksploruj**,aby otworzyć folder **\<Drive\>: \\AosService\\WebRoot**. Znajdź plik **wif.config**.

    ![Plik Wif.config w folderze WebRoot.](./media/setup_rsa_tool_50.png)

4. Zaktualizuj plik **wif.config**, dodając nowy wpis urzędu dla swojego certyfikatu i nazwę urzędu tak jak w następującym przykładzie.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Jeśli wielu użytkowników korzysta z tej samej aplikacji, każdy użytkownik musi wygenerować własny odcisk palca, a każdy z tych odcisków palców musi zostać dodany w sekcji **\<keys\>**.

5. Jeśli jest więcej niż jeden komputer AOS, wykonaj kroki od 3 do 4 z każdym dodatkowym komputerem.

    > [!NOTE]
    > W przeciwieństwie do starszych środowisk warstwy 2 nowe środowiska warstwy 2 są wdrażane z dwoma wystąpieniami serwera AOS.

6. Uruchom polecenie **iisreset** na wszystkich komputerach AOS.

    > [!NOTE]
    > Jeśli nie masz uprawnień administratora do uruchamiania polecenia **iisreset** na komputerze warstwy 1, na stronie Szczegóły środowiska w usłudze LCS wybierz opcję Zarządzaj > Uruchom ponownie usługi.

#### <a name="tier-2-environment"></a>Środowisko warstwy 2 lub wyższej

Jeśli jest używane środowisko rozwiązania warstwy 2 lub wyższej (piaskownica testowania akceptacji wersji Standard lub wyższa warstwa), potwierdź lub wprowadź następujące ustawienie rejestru na komputerze, na którym jest zainstalowane narzędzie RSAT. Ten krok jest wymagany, ponieważ może pozwolić uniknąć błędów związanych z uwierzytelnianiem lub z połączeniem z narzędziem RSAT.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Instalowanie narzędzia RSAT

1. Przejdź do strony <https://www.microsoft.com/download/details.aspx?id=57357> i kliknij przycisk **Pobierz**.
2. Zaznacz wszystkie pliki, a następnie kliknij przycisk **Dalej**.

    ![Zaznaczanie wszystkich plików.](./media/setup_rsa_tool_51.png)

3. Kliknij dwukrotnie pakiet MSI, aby uruchomić instalatora. Następnie, po zakończeniu instalacji, kliknij przycisk **Zakończ**.

    ![Plik instalatora narzędzia RSAT.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Instalowanie sterownika Selenium i sterowników przeglądarki

W starszych wersjach narzędzia RSAT konieczne było instalowanie sterownika Selenium i sterowników przeglądarki. Instalowanie tych sterowników nie jest konieczne, ponieważ są one instalowane automatycznie.

1. Podczas uruchamiania narzędzia RSAT po raz pierwszy system wyświetli monit o automatyczne pobranie i zainstalowanie sterownika Selenium. Aby uzyskać więcej informacji, zobacz sekcję [Konfigurowanie narzędzia RSAT](#configure-rsat).
2. Przed uruchomieniem przypadku testowego wyświetlany jest monit o automatyczne pobranie i zainstalowanie sterownika przeglądarki do domyślnej przeglądarki, która została wybrana w konfiguracji narzędzia RSAT. Aby uzyskać więcej informacji, zobacz sekcję [Ładowanie i uruchamianie przypadków testowych](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Rozpoczęcie korzystania z narzędzia RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Tworzenie planu testów i pakietów testów

1. Przejdź do projektu usługi Azure DevOps i wybierz polecenie **Plany testów**.

    ![Polecenie Plany testów.](./media/setup_rsa_tool_53.png)

2. Kliknij przycisk **Nowy plan testów**

    ![Przycisk Nowy plan testów.](./media/setup_rsa_tool_54.png)

3. Wypełnij pole **Nazwa**, a następnie kliknij przycisk **Utwórz**. Nazwa planu testów w tym samouczku to **Plan testów RSAT**.

    ![Okno dialogowe Nowy plan testów.](./media/setup_rsa_tool_55.png)

4. Kliknij znak plus (**+**), a następnie kliknij przycisk **Pakiet statyczny**, aby utworzyć pakiet statyczny w ramach nowego planu testów. Nazwij nowy pakiet testów **T01 – Produkcja na magazyn**.

    > [!NOTE]
    > Możesz również utworzyć pakiet oparty na kwerendach, jeśli nowe przypadki testowe z narzędzia BPM mają być automatycznie wciągane do pakietu testów narzędzia RSAT.

    ![Tworzenie pakietu statycznego.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Dołączanie przypadków testowych do pakietu testów

1. Kliknij przycisk **Dodaj istniejące** po prawej stronie, aby dodać istniejące przypadki testowe do pakietu testów.

    ![Przycisk Dodaj istniejące.](./media/setup_rsa_tool_57.png)

2. Na stronie **Dodawanie przypadków testowych do pakietu** kliknij przycisk **Uruchom kwerendę**, a następnie wybierz przypadek testowy, który ma zostać dodany do pakietu testów. W tym samouczku wybierz przypadek testowy **Tworzenie nowego produktu**. Następnie kliknij przycisk **Dodaj przypadki testowe** w prawym dolnym rogu strony (ten przycisk nie jest widoczny na ilustracji)

    ![Przycisk Uruchom kwerendę.](./media/setup_rsa_tool_58.png)

    Przypadek testowy zostanie dodany do pakietu testów **T01- Produkcja na magazyn**.

    ![Przypadek testowy dodany do pakietu testów.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Konfiguruj usługę RSAT

1. Otwórz narzędzie RSAT.

    ![Ikona RSAT.](./media/setup_rsa_tool_60.png)

2. Zostanie wyświetlony komunikat ostrzegawczy „Regression Suite Automation Tool wymaga sterownika Selenium. Czy chcesz go automatycznie pobrać i zainstalować?” Wybierz opcję **Tak**.

    ![Komunikat ostrzegawczy o tym, że narzędzie Regression Suite Automation Tool wymagający sterownika Selenium.](./media/setup_rsa_tool_61.png)

3. Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu, a następnie w wyświetlonym oknie dialogowym wypełnij następujące pola:

    - **Adres URL usługi Azure DevOps** — wprowadź adres URL projektu usługi Azure DevOps, jak `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Token dostępu** — wprowadź token dostępu, na mocy którego narzędzie łączy się z usługą Azure DevOps. Użyj osobistego tokenu dostępu utworzonego wcześniej w tym samouczku. Aby uzyskać więcej informacji, zobacz sekcję [Uwierzytelnianie dostępu za pomocą osobistych tokenów dostępu](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Nazwa projektu** — wybierz nazwę danego projektu usługi Azure DevOps.
    - **Plan testów** — wybierz plan testów usługi Azure DevOps, który zawiera przypadki testowe. Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie planu testów i pakietów testów](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Po wybraniu planu testów kliknij przycisk **Testuj połączenie**, aby przetestować połączenie z usługą Azure DevOps.
    - **Nazwa hosta** — wprowadź nazwę hosta środowiska rozwiązania Finance and Operations, np. **\<myaos\>.cloudax.dynamics.com**. Nie należy dodawać prefiksu **https://** ani **http://**.
    - **Nazwa hosta SOAP** — wprowadź nazwę hosta SOAP środowiska testowego. Zazwyczaj nazwa hosta SOAP jest taka sama jak nazwa hosta, ale ma sufiks **soap**. Oto przykład: **\<myaos\>soap.cloudax.dynamics.com**. Nie należy dodawać prefiksu **https://** ani **http://**.

        > [!NOTE]
        > Aby znaleźć nazwę hosta i nazwę hosta SOAP, otwórz Menedżera IIS, kliknij prawym przyciskiem myszy pozycję **Witryny \> AOSService**, a następnie wybierz polecenie **Edytuj powiązania**. Wartości w kolumnie **Nazwa hosta** zawierają nazwę hosta i nazwę hosta SOAP (nazwa hosta SOAP ma sufiks **SOAP** w adresie URL).

        ![Nazwa hosta i nazwa hosta SOAP w kolumnie Nazwa hosta.](./media/setup_rsa_tool_63.png)

    - **Nazwa użytkownika administratora** — wprowadź adres e-mail użytkownika administratora w środowisku testowym.
    - **Odcisk palca** — wprowadź odcisk palca certyfikatu uwierzytelniania, jak opisano wcześniej w tym samouczku.
    - **Katalog roboczy** — określ lokalizację folderu przechowywania plików automatyzacji testów, takich jak pliki danych testowych programu Excel. Na przykład wprowadź lub wybierz katalog **C:\\Temp\\RegressionTool**.

        > [!NOTE]
        > Jeśli nazwa folderu zawiera spacje, wykonanie nie powiedzie się z powodu nieznalezienia folderu. Ten błąd jest znany i powinien zostać naprawiony w najnowszej wersji narzędzia.

    - **Domyślna przeglądarka** — wybierz opcję **Internet Explorer** lub **Google Chrome**. Upewnij się, że zostały zainstalowane odpowiednie sterowniki przeglądarki.
    - **Limit czasu przebiegu testowego** — określ limit czasu trwania (w minutach) przebiegów testowych. Po upływie limitu czasu wszystkie aktywne okna są zamykane i oczekujące przypadki testowe kończą się niepowodzeniem.
    - **Limit czasu akcji testowej** — to pole określa limit czasu (w minutach) żądań serwera środowiska operacyjnego rozwiązania Finance and Operations. Zazwyczaj wartość domyślna (2 minuty) powinna być wystarczająca. Jednak w przypadku wolniejszych środowisk można zwiększyć wartość, jeśli występują błędy związane z przekroczeniem limitu czasu.
    - **Nazwa firmy** — wprowadź nazwę firmy używanej jako domyślna firma podczas tworzenia plików parametrów programu Excel. Firmę można później zmienić, edytując plik parametrów programu Excel.

    ![Okno dialogowe Ustawienia.](./media/setup_rsa_tool_62.png)

4. Kliknij przycisk **Zastosuj**, aby zastosować i zapisać ustawienia.

    Aby zapisać bieżące ustawienia w pliku konfiguracji na komputerze, kliknij przycisk **Zapisz jako**. Aby przywrócić ustawienia z pliku konfiguracji na komputerze, kliknij przycisk **Otwórz**.

5. Kliknij przycisk **Zamknij**, aby zamknąć okno dialogowe.

### <a name="load-and-run-test-cases"></a>Ładowanie i uruchamianie przypadków testowych

1. Kliknij przycisk **Załaduj**, aby załadować **Plan testów narzędzia RSAT** z projektu usługi Azure DevOps

    ![Przycisk Załaduj.](./media/setup_rsa_tool_64.png)

2. Wybierz przypadek testowy **Tworzenie nowego produktu** z pakietu testów, a następnie wybierz opcje **Nowy \> Generuj pliki wykonania testu i parametrów**.

    ![Polecenie Generuj pliki wykonania testu i parametrów w menu Nowy.](./media/setup_rsa_tool_65.png)

    Plik parametrów programu Excel zostanie utworzony w folderze lokalnym określonym w konfiguracji narzędzia RSAT (na przykład **C:\\temp\\RegressionTool**).

    ![Utworzony plik parametrów programu Excel.](./media/setup_rsa_tool_66.png)

3. Jeśli chcesz zapisać pliki parametrów, kliknij przycisk **Przekaż**. Pliki automatyzacji testów wszystkich wybranych przypadków testowych zostaną przekazane do usługi Azure DevOps do ewentualnego użycia w przyszłości. (Te pliki zawierają pliki parametrów testowych programu Excel)

    W ten sposób można kliknąć przycisk **Załaduj**, aby załadować pliki parametrów (i pliki automatyzacji) z przypadku testowego bezpośrednio z usługi Azure DevOps. Nie ma konieczności ponownego generowania plików parametrów. Ta metoda będzie przydatna w przyszłości, jeśli chcesz zachowywać modyfikacje w pliku parametrów i nie chcesz, aby były one zastępowane.

4. Aby sprawdzić, czy pliki automatyzacji i pliki parametrów są zapisane w usłudze Azure DevOps, przejdź do projektu usługi Azure DevOps, wybierz opcje **Tablice \> Elementy robocze** i wybierz przypadek testowy **Tworzenie nowego produktu**. Na karcie **Załączniki** powinny być widoczne cztery pliki:

    - **.cs** — plik automatyzacji C\#
    - **.dll** — skompilowany plik automatyzacji jako zestaw
    - **.xlsx** — plik parametrów programu Excel
    - **.xml** – plik nagrania

    ![Pliki na karcie Załączniki.](./media/setup_rsa_tool_67.png)

5. Wybierz przypadek testowy, który ma zostać uruchomiony, a następnie kliknij przycisk **Uruchom**.

    > [!NOTE]
    > W przypadku korzystania z przeglądarki Internet Explorer przed uruchomieniem przypadków testowych należy upewnić się, że jako rozdzielczość pulpitu wybrano wartość **100%** w sekcji **Ustawienia ekranu systemu Windows \> Skala i układ**. Jeśli nie możesz zmienić tego ustawienia na maszynie wirtualnej (VM), zmień ją na kliencie (laptopie), z którego próbujesz uzyskać dostęp do maszyny wirtualnej. Ustawienia rozdzielczości zostaną wówczas odziedziczone przez ustawienia ekranu maszyny wirtualnej.

    ![Ustawienie 100% rozdzielczości pulpitu.](./media/setup_rsa_tool_68.png)

6. Jeśli sterowniki przeglądarki nie są zainstalowane w systemie, zostanie wyświetlony komunikat ostrzegawczy „Ta operacja wymaga sterownika \<browser name\>. Czy chcesz automatycznie pobrać i zainstalować go teraz?” Wybierz opcję **Tak**.

    ![Komunikat ostrzegawczy dotyczący programu Internet Explorer.](./media/setup_rsa_tool_69.png)

    ![Komunikat ostrzegawczy dotyczący programu Chrome.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Jeśli korzystasz z przeglądarki Chrome i zostanie wyświetlony komunikat o błędzie informujący o nieutworzeniu sesji z powodu niepoprawnej wersji programu Chrome, pobierz najnowszy sterownik programu Chrome ze strony <http://chromedriver.chromium.org/downloads> do folderu **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.

    ![Komunikat o błędzie dotyczący programu Chrome.](./media/setup_rsa_tool_71.png)

    Przypadek testowy zostanie uruchomiony, a pole **Wynik** zostanie zaktualizowane.

    ![Zaktualizowane pole wyniku.](./media/setup_rsa_tool_72.png)

    Jeśli postępujesz dokładnie według tego samouczka, przypadek testowy **Tworzenie nowego produktu** nie powiedzie się, ponieważ w nagraniu zadania tworzenia produktu nazwa produktu została zapisana jako wartość niezmienna. Jeśli ten sam przypadek testowy zostanie ponownie uruchomiony, powinien zostać wyświetlony komunikat o błędzie, ponieważ produkt już istnieje.

    ![Pole Wynik z ustawieniem Niepowodzenie.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Wyświetlanie wyników testu

1. Kliknij dwukrotnie przypadek testowy zakończony niepowodzeniem.

    Zostanie wyświetlony komunikat o błędzie.

    ![Komunikat o błędzie.](./media/setup_rsa_tool_73.png)

2. Kliknij przycisk **Szczegóły**, aby wyświetlić cały komunikat o błędzie.

    ![Cały komunikat o błędzie.](./media/setup_rsa_tool_74.png)

3. Aby wyświetlić szczegółową wersję komunikatu o błędzie w usłudze Azure DevOps, kliknij przycisk **Otwórz w usłudze Azure DevOps**. W usłudze Azure DevOps można wyświetlić stan przypadku testowego i szczegółowy komunikat o błędzie.

    ![Szczegółowy komunikat o błędzie w usłudze Azure DevOps.](./media/setup_rsa_tool_75.png)

4. Aby wyświetlić wyniki testów bezpośrednio w projekcie usługi Azure DevOps, wybierz kolejno opcje do **Plany testów \> Plany testów \> Przebiegi**. Kliknij dwukrotnie przebieg testowy, o którym chcesz wyświetlić więcej szczegółów.

    ![Lista przebiegów testowych w usłudze Azure DevOps.](./media/setup_rsa_tool_76.png)

5. Na karcie **Podsumowanie przebiegu** jest wskazane niepowodzenie przypadku testowego, ale nie jest wyświetlany sam komunikat o błędzie. Aby wyświetlić szczegółowy komunikat o błędzie, kliknij kartę **Wyniki testów**.

    ![Karta Podsumowanie przebiegu.](./media/setup_rsa_tool_77.png)

    Karta **Wyniki testów** zawiera informacje o przypadku testowym wraz z wynikami i komunikatem o błędzie.

    ![Karta Wyniki testów.](./media/setup_rsa_tool_78.png)

6. Kliknij dwukrotnie odpowiedni rekord, aby wyświetlić szczegółowy komunikat o błędzie.

    ![Szczegółowy komunikat o błędzie.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Wszystkie komunikaty o błędzie są również dostępne lokalnie w folderze **C:\\Users\\\$Twoja_nazwa_użytkownika\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. Wyniki przebiegu testowego można również wyeksportować z poziomu planu testów, klikając przycisk **Eksportuj**.

    ![Eksportowanie planu testów.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modyfikowanie pliku parametrów programu Excel

1. Otwórz narzędzie RSAT.
2. Wybierz przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć plik parametrów programu Excel.

    W arkuszu **EcoResProductCreate** jest widoczne, że wartość pola **Numer produktu** jest niezmienna. Musisz wprowadzić w tym polu nową nazwę produktu, aby można było ponownie uruchomić przypadek testowy.

3. Aby podczas każdego uruchomienia był generowany unikatowy numer produktu bez konieczności ponownego otwierania pliku parametrów programu Excel i ręcznego zmieniania numeru produktu za każdym razem, należy wprowadzić następującą formułę programu Excel.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Oprócz karty **Ogólne** plik parametrów programu Excel zawiera kartę Dane dla każdej strony formularza, która jest odwiedzana przez przypadek testowy.

    ![Pole Numer produktu.](./media/setup_rsa_tool_81.png)

4. Kliknij przycisk **Zapisz**, a następnie zamknij skoroszyt programu Excel.
5. Kliknij przycisk **Przekaż**, aby zapisać plik parametrów programu Excel w usłudze Azure DevOps.

    ![Komunikat o przekazaniu pliku.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Aby uruchomić przypadki testowe w określonym kontekście użytkownika, należy wprowadzić identyfikator e-mail użytkownika w polu **Użytkownik testowy** na karcie **Ogólne** pliku parametrów programu Excel. W najnowszej wersji narzędzia RSAT zmieniono układ pól w pliku parametrów programu Excel, ale ogólna zasada pozostała taka sama.
    >
    > ![Pole Użytkownik testowy.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Sprawdzanie poprawności wyników

- Kliknij przycisk **Uruchom**, aby ponownie uruchomić przypadek testowy i sprawdź, czy przypadek testowy został zaliczony. Wyniki testów można wyświetlać w sposób opisany w sekcji [Wyświetlanie wyników testów](#view-the-test-results).

    ![Pole Wynik z ustawieniem Powodzenie.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Łączenie przypadków testowych w łańcuchy

Jedną z najważniejszych funkcji narzędzia RSAT jest łączenie przypadków testowych w łańcuchy (to znaczy zdolność testu do przekazywania wartości do innych testów). Przypadki testowe są uruchamiane w kolejności określonej w planie testów usługi Azure DevOps. (Ta kolejność może również zostać zaktualizowana w samym narzędziu testowym). Dlatego, jeśli zmienne mają być przekazywane z jednego przypadku testowego do innego, bardzo ważne jest, aby testy były wykonywane we właściwej kolejności.

W tej sekcji utworzysz zapisaną zmienną w pierwszym przypadku testowym, utworzysz drugi przypadek testowy i przekażesz zapisaną zmienną z pierwszego przypadku testowego do drugiego przypadku testowego. Następnie uruchomisz przypadki testowe jako łańcuch przypadków testowych w narzędziu RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej

1. Otwórz klienta.
2. Kliknij przycisk **Ustawienia** (symbol koła zębatego), a następnie kliknij przycisk **Rejestrator zadań**.
3. Kliknij przycisk **Edytuj nagranie**.

    ![Przycisk Edytuj nagranie.](./media/setup_rsa_tool_85.png)

4. Kliknij przycisk **Otwórz z usługi Lifecycle Services**.

    ![Przycisk Otwórz z usługi Lifecycle Services.](./media/setup_rsa_tool_86.png)

5. Kliknij przycisk **Wybierz bibliotekę usługi Lifecycle Services**.

    ![Przycisk Wybierz bibliotekę usługi Lifecycle Services.](./media/setup_rsa_tool_87.png)

    Biblioteki narzędzia BPM zostaną załadowane z usługi LCS.

    ![Ładowanie bibliotek narzędzia BPM.](./media/setup_rsa_tool_88.png)

6. Po załadowaniu bibliotek narzędzia BPM z usługi LCS wybierz bibliotekę narzędzia BPM **RSAT** i proces biznesowy **Tworzenie nowego produktu**, z którym skojarzono to nagranie zadania. Następnie wybierz opcję **OK**.

    ![Wybieranie biblioteki BPM i procesu biznesowego.](./media/setup_rsa_tool_89.png)

7. Nazwa odpowiedniego nagrania zadania jest wprowadzana w polu **Nazwa nagrania**. Wybierz **Start**.

    ![Pole nagrania zadania w polu Nazwa nagrania.](./media/setup_rsa_tool_90.png)

8. Wybierz opcje **Zarządzanie informacjami o produktach \> Produkty** i kliknij przycisk **Nowy**, aby otworzyć stronę, na której zarejestrowano oryginalne nagranie zadania **Tworzenie produktu**.
9. Kliknij przycisk **Wstaw krok**.

    > [!NOTE]
    > Nowy krok zostanie wstawiony **po** kroku wybranym w okienku.

    ![Przycisk Wstaw krok.](./media/setup_rsa_tool_91.png)

10. Kliknij prawym przyciskiem myszy pole **Numer produktu**, a następnie wybierz opcje **Rejestrator zadań \> Kopiuj**.

    ![Polecenie Kopiuj.](./media/setup_rsa_tool_92.png)

11. W okienku zostanie dodany nowy krok. Zanotuj wartość w polu **Numer produktu**, ponieważ będzie ona potrzebna później.

    ![Dodany nowy krok.](./media/setup_rsa_tool_93.png)

12. Kliknij przycisk **Zakończono edycję**.
13. Kliknij przycisk **Zapisz w usłudze Lifecycle Services** i skojarz nowe nagranie zadania z tą samą biblioteką narzędzia BPM i procesem biznesowym, z którymi było skojarzone oryginalne nagranie zadania. Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Przejdź do biblioteki narzędzia BPM i kliknij przycisk **Synchronizuj przypadki testowe**, aby zastąpić nagranie zadania dołączone do przypadku testowego w usłudze Azure DevOps, zgodnie z opisem w sekcji [Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Otwórz narzędzie RSAT i kliknij przycisk **Załaduj**, aby ponownie załadować przypadki testowe z pakietu testów. Musisz ponownie wygenerować pliki automatyzacji i parametrów odpowiedniego przypadku testowego, wybierając przypadek testowy, a następnie wybierając opcje **Nowy \> Generuj pliki wykonania testu i parametrów** zgodnie z opisem w sekcji [Ładowanie i uruchamianie przypadków testowych](#load-and-run-test-cases).

    > [!NOTE]
    > Jeśli pozostawiono otwarty plik parametrów programu Excel, ponowne generowanie nie powiedzie się. Dlatego należy pamiętać o zamknięciu pliku parametrów programu Excel przypadku testowego przed generowaniem nowego pliku parametrów programu Excel.

16. Kliknij przycisk **Edytuj**, aby otworzyć nowy plik parametrów programu Excel. W wierszu 9 zostanie wyświetlony nowy wpis **Zapisana zmienna**. Ta zmienna, **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}**, jest zapisywana w pliku XML nagrania zadania i może być używana w kolejnych testach.

    ![Wpis zapisanej zmiennej.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Tworzenie nowego przypadku testowego

1. Przejdź do biblioteki narzędzia BPM **RSAT**.
2. Wybierz proces **Przykładowy pomocniczy proces biznesowy**, a następnie kliknij przycisk **Tryb edycji** po prawej stronie.
3. Zmień wartość w polach **Nazwa** i **Opis** na **Wydanie produktu**. Następnie kliknij przycisk **Zapisz**.

    ![Nazwa i opis zostały zmienione na Wydanie produktu.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Tworzenie nowego nagrania zadania z funkcją sprawdzania poprawności

- Utwórz nagranie zadania, aby wydać utworzony wcześniej produkt firmie USRT. Aby uzyskać więcej informacji, zobacz sekcję [Tworzenie nagrania zadania i zapisywanie go w bibliotece narzędzia BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > W przypadku przypadków testowych połączonych w łańcuch zawsze zaleca się znalezienie lub przefiltrowanie wymaganego rekordu przez *ręczne wpisanie wartości pola*. W ten sposób narzędzie może określić rekord, na którym ma zostać wykonana akcja w kolejnym przypadku testowym.

    ![Nowe nagranie zadania z funkcją sprawdzania poprawności.](./media/setup_rsa_tool_96.png)

    Jak widać na poprzedniej ilustracji, gdy produkt zostanie znaleziony przy użyciu szybkiego filtra, ale przed wybraniem polecenia **Wydaj produkty**, sprawdzasz wartość pola **Numer produktu**, aby upewnić się, że identyfikator produktu jest tym samym identyfikatorem produktu, który został utworzony wcześniej. Aby sprawdzić poprawność wartości, kliknij prawym przyciskiem myszy pole **Numer produktu**, a następnie wybierz kolejno opcje **Rejestrator zadań \> Sprawdź poprawność \> Bieżąca wartość**.

    ![Sprawdzanie poprawności bieżącej wartości.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Zapisywanie nagrania zadania w narzędziu BPM

1. Po zakończeniu rejestrowania zadania kliknij przycisk **Zapisz w usłudze Lifecycle Services**.

    ![Zapisz zakończone nagranie zadania w usługach Lifecycle Services.](./media/setup_rsa_tool_98.png)

2. Informacje o bibliotece zostaną załadowane z usługi LCS.

    ![Ładowanie informacji o bibliotece z usług LCS.](./media/setup_rsa_tool_99.png)

3. Wybierz bibliotekę narzędzia BPM do skojarzenia z nagraniem zadania. W tym samouczku wybierz bibliotekę **RSAT** narzędzia BPM, która została utworzona wcześniej, oraz należący do niej proces biznesowy **Wydanie produktu**. Następnie wybierz opcję **OK**.

#### <a name="sync-bpm-to-azure-devops"></a>Synchronizuj narzędzie BPM z usługą Azure DevOps

1. Przejdź do biblioteki narzędzia BPM i otwórz bibliotekę **RSAT**.
2. Kliknij przycisk **Synchronizacja z usługą VSTS**, a następnie **Synchronizuj przypadki testowe**. Aby uzyskać więcej informacji, zobacz sekcję [Testowanie synchronizacji narzędzia BPM z usługą Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).

    Po zakończeniu synchronizacji nowy element roboczy i odpowiedni przypadek testowy procesu biznesowego **Wydanie produktu** zostanie wyświetlony w sekcji **Tablice \> Elementy robocze** usługi Azure DevOps.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Dodawanie nowego przypadku testowego do istniejącego pakietu testów

1. Wybierz opcje **Plany testów \> Plany testów** i wybierz plan **Plan testów RSAT**.
2. Kliknij przycisk **Dodaj istniejące**.
3. Na stronie **Dodawanie przypadków testowych do pakietu** kliknij przycisk **Uruchom kwerendę**.
4. Wybierz nowy przypadek testowy, który został utworzony dla procesu **Wydanie produktu**, a następnie kliknij przycisk opcję **Dodaj przypadki testowe** w prawym dolnym rogu strony (ten przycisk nie jest widoczny na ilustracji)

    ![Strona Dodawanie przypadków testowy do pakietu.](./media/setup_rsa_tool_100.png)

    Pakiet testów zawiera teraz dwa przypadki testowe.

    ![Dwa przypadki testowe w pakiecie testów.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Ładowanie przypadków testowych do narzędzia RSAT

1. Otwórz narzędzie RSAT i kliknij przycisk **Załaduj**.
2. Przypadki testowe zostaną załadowane i zostanie wyświetlone ostrzeżenie „Ta akcja spowoduje zastąpienie plików danych testowych programu Excel, zmiany lokalne zostaną utracone. Czy chcesz kontynuować?” Kliknij przycisk **Tak**, aby zaktualizować pliki parametrów programu Excel w systemie lokalnym, ale nie pliki parametrów programu Excel, które zostały przekazane do usługi Azure DevOps.

    ![Ta akcja spowoduje zastąpienie plików danych testowych programu Excel.](./media/setup_rsa_tool_102.png)

    Oba przypadki testowe zostaną załadowane wraz z plikiem parametrów programu Excel pierwszego przypadku testowego. Z powodu kliknięcia w ostatnim przebiegu przycisku **Przekaż** pliki parametrów są ściągane z usługi Azure DevOps.

    ![Przypadki testowe załadowane.](./media/setup_rsa_tool_103.png)

3. Wybierz tylko drugi przypadek testowy, a następnie wybierz opcje **Nowy \> Generuj pliki wykonania testu i parametrów**.

#### <a name="edit-the-excel-parameter-file"></a>Edytowanie pliku parametrów programu Excel

1. Wybierz tylko drugi przypadek testowy, a następnie kliknij przycisk **Edytuj**, aby otworzyć odpowiedni plik parametrów programu Excel.
2. Skopiuj zapisaną zmienną **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (zobacz sekcję the [Modyfikowanie istniejącego nagrania zadania w celu utworzenia zapisanej zmiennej](#modify-an-existing-task-recording-to-create-a-saved-variable)) z pierwszego przypadku testowego do wszystkich pól, w których jest używany numer produktu. W tej sytuacji należy skopiować zmienną do pól **Numer produktu** i **Sprawdź poprawność numeru produktu** na arkuszu **EcoResProductListPage**.

    ![Pola Numer produktu i Sprawdź poprawność numeru produktu.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Zmienne mogą być przekazywane między testami tylko podczas tego samego przebiegu testu. Nazwy zmiennych muszą być dokładnie takie same.

3. Kliknij przycisk **Zapisz**, a następnie zamknij skoroszyt programu Excel.
4. Kliknij przycisk **Przekaż**, aby zapisać dokonane zmiany w pliku parametrów programu Excel.

#### <a name="run-the-chained-test-cases"></a>Uruchamianie połączonych w łańcuch przypadków testowych

1. Wybierz oba przypadki testowe, a następnie kliknij przycisk **Uruchom**.
2. Sprawdź, czy oba przypadki testowe zostały zaliczone.

    ![Pole Wynik z ustawieniem Powodzenie obu przypadków testowych.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]