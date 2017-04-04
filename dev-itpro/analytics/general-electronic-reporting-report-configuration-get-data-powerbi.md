---
title: "Ustawianie elektronicznej zgłoszenie dostarczanie Power BI danych z systemu Dynamics 365 dla operacji"
description: "W tym temacie wyjaśniono sposób wykorzystania konfiguracji raportowania elektronicznego (ER) do organizowania przesyłania danych z wystąpienia programu Dynamics 365 for Operations do usług Power BI. Na potrzeby przykładu użyto transakcji Intrastat jako danych biznesowych, które muszą zostać przesłane. Funkcja wizualizacja mapy w programie Power BI wykorzystuje te dane transakcji Intrastat do przedstawienia widoku umożliwiającego analizę działań importowych/eksportowych firmy w raporcie programu Power BI."
author: kfend
manager: AnnBe
ms.date: 2016-10-31 13 - 22 - 29
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: ed0192c44b6d7e88120c64e539ebb0ac3b379831
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-electronic-reporting-to-provide-power-bi-with-data-from-dynamics-365-for-operations"></a>Ustawianie elektronicznej zgłoszenie dostarczanie Power BI danych z systemu Dynamics 365 dla operacji

W tym temacie wyjaśniono sposób wykorzystania konfiguracji raportowania elektronicznego (ER) do organizowania przesyłania danych z wystąpienia programu Dynamics 365 for Operations do usług Power BI. Na potrzeby przykładu użyto transakcji Intrastat jako danych biznesowych, które muszą zostać przesłane. Funkcja wizualizacja mapy w programie Power BI wykorzystuje te dane transakcji Intrastat do przedstawienia widoku umożliwiającego analizę działań importowych/eksportowych firmy w raporcie programu Power BI.

<a name="overview"></a>Przegląd
--------

Microsoft Power BI to zbiór usług oprogramowania, aplikacji i łączników, które wspólnie wydobywają z zewnętrznych źródeł danych spójne, realistyczne wizualnie i interaktywne wnioski. Moduł Raportowanie elektroniczne (ER) pozwala użytkownikom programu Microsoft Dynamics 365 for Operations łatwo konfigurować źródła danych i organizować przesyłanie danych z programu Dynamics 365 for Operations do programu Power BI. Dane są przesyłane jako pliki w formacie arkusza OpenXML (plik skoroszytu programu Microsoft Excel). Przesłane pliki są przechowywane na serwerze programu Microsoft SharePoint, który został skonfigurowany do tego celu. Przechowywane pliki są używane w programie Power BI do tworzenia raportów zawierających wizualizacje (tabele, wykresy, mapy i tak dalej). Raporty programu Power BI są udostępniane użytkownikom programu Power BI i można je otwierać w pulpitach nawigacyjnych programu Power BI i na stronach programu Dynamics 365 for Operations. W tym temacie wyjaśniono następujące zadania:

-   Konfigurowanie programu Dynamics 365 for Operations.
-   Przygotowywanie konfiguracji formatu ER do pobierania danych z programu Dynamics 365 for Operations.
-   Skonfigurowanie środowiska ER do przesyłania danych do programu Power BI.
-   Używanie przesłanych danych do tworzenia raportu programu Power BI.
-   Udostępnianie raportów programu Power BI w programie Dynamics 365 for Operations.

## <a name="prerequisites"></a>Wymagania wstępne
Aby wykonać przykład opisany w tym temacie, musisz mieć następujące uprawnienia dostępu:

-   Dostęp do programu Dynamics 365 for Operations w jednej z następujących ról:
    -   Deweloper raportowania elektronicznego
    -   Konsultant funkcjonalny raportowania elektronicznego
    -   Administrator systemu
-   Dostęp do serwera programu SharePoint, który jest skonfigurowany do współpracy z programem Dynamics 365 for Operations.
-   Dostęp do środowiska programu Power BI.

## <a name="configure-document-management-parameters"></a>Konfigurowanie parametrów zarządzania dokumentami
1.  Na stronie **Parametry zarządzania dokumentami** skonfiguruj dostęp do serwera programu SharePoint, który będzie używany w firmie, do której się logujesz (w tym przykładzie jest to firma DEMF).
2.  Przetestuj połączenie z serwerem programu SharePoint, aby się upewnić, że przyznano Ci dostęp. [![Strona parametrów zarządzania dokumentu](./media/ger-power-bi-sharepoint-server-setting-1024x369.png)](./media/ger-power-bi-sharepoint-server-setting.png)
3.  Otwórz skonfigurowaną witrynę programu SharePoint. Utwórz nowy folder, gdzie moduł ER będzie przechowywał pliki programu Excel zawierające dane biznesowe, których raporty programu Power BI wymagają jako źródła zestawów danych.
4.  W programie Dynamics 365 for Operations na stronie **Typy dokumentów** utwórz nowy typ dokumentu, który będzie używany w celu uzyskiwania dostępu do nowo utworzonego folderu programu SharePoint. Wpisz **Plik** w polu **Grupa** i **SharePoint** w polu **Lokalizacja**, a następnie wprowadź adres folderu programu SharePoint. [![Strona typów dokumentu](./media/ger-power-bi-sharepoint-document-type-1024x485.png)](./media/ger-power-bi-sharepoint-document-type.png)

## <a name="configure-er-parameters"></a>Konfigurowanie parametrów modułu ER
1.  W obszarze roboczym **Raportowanie elektroniczne** kliknij łącze **Parametry raportowania elektronicznego**.
2.  Na karcie **Załączniki** wybierz typ dokumentu **Plik** we wszystkich polach.
3.  W obszarze roboczym **Raportowanie elektroniczne** uaktywnij wymaganego dostawcę przez kliknięcie przycisku **Ustaw jako aktywny**. Aby uzyskać więcej informacji, odtwórz przewodnik po zadaniu **ER Wybór dostawcy usług**.

## <a name="use-an-er-data-model-as-the-source-of-data"></a>Używanie modelu danych raportowania elektronicznego jako źródła danych
Model danych ER musi być źródłem danych biznesowych, które będą używane w raportach programu Power BI. Ten model danych jest wczytywany z repozytorium konfiguracji raportowania elektronicznego. Aby uzyskać więcej informacji, zobacz [Pobieranie konfiguracji modułu Raportowanie elektroniczne z usługi Lifecycle Services](download-electronic-reporting-configuration-lcs.md) lub odtwórz przewodnik po zadaniu **ER Importowanie konfiguracji z usługi Lifecycle Services**. Wybierz **Intrastat** jako modelu danych, który zostanie wczytany z wybranego repozytorium konfiguracji modułu ER. (W tym przykładzie model w wersji 1 jest używana.) Następnie można uzyskać dostęp **Intrastat** konfiguracji modelu encja-Relacja na **konfiguracje** strony. [![Strona konfiguracji](./media/ger-power-bi-data-model-1024x371.png)](./media/ger-power-bi-data-model.png)

## <a name="design-an-er-format-configuration"></a>Projektowanie konfiguracji formatu raportowania elektronicznego
Należy utworzyć nową konfigurację formatu modułu ER używającą modelu danych **Intrastat** jako źródła danych biznesowych. Ta konfiguracja formatu musi generować dane wyjściowe w postaci dokumentów elektronicznych w formacie OpenXML (pliku programu Excel). Aby uzyskać więcej informacji, odtwórz przewodnik po zadaniu **ER Tworzenie konfiguracji dla raportów w formacie OPENXML**. Nazwij nową konfigurację **Działania importu/eksportu**, jak pokazano na poniższej ilustracji. Użyj pliku programu Excel [Dane ER — szczegóły importu i eksportu](https://go.microsoft.com/fwlink/?linkid=845208) jako szablonu podczas projektowania formatu ER. (Aby uzyskać informacje o tym, jak można zaimportować szablon format, odtwarzać przewodnik zadania). [![Importu / Eksportuj konfigurację działalności](media/ger-power-bi-format-configuration.png)](media/ger-power-bi-format-configuration.png) do modyfikowania **Import / export działalności** format konfiguracji, wykonaj następujące kroki.

1.  Kliknij przycisk **Konstruktor**.
2.  Na karcie **Format** nazwij plikowy element tego formatu jako **Plik wyjściowy programu Excel**. [![Element pliku danych wyjściowych programu Excel](./media/ger-power-bi-format-configuration-file-element-name-1024x395.png)](./media/ger-power-bi-format-configuration-file-element-name.png)
3.  Na karcie **Mapowanie** określ nazwę pliku programu Excel, który będzie generowany przy każdym uruchomieniu tego formatu. Skonfiguruj pokrewne wyrażenie, aby zwracało wartość **Szczegóły importu i eksportu** (rozszerzenie nazwy pliku .xlsx zostanie dodane automatycznie). [![Format designer](./media/ger-power-bi-format-configuration-output-file-name-1024x396.png)](./media/ger-power-bi-format-configuration-output-file-name.png)
4.  Dodaj nowy element źródła danych dla tego formatu. (Ten element stałotekstowy będzie wymagany przy dalszym wiązaniu danych).
    1.  Nazwa źródła danych **kierunek\_enum**.
    2.  Jako typ źródła danych wybierz **Wyliczenie modeli danych**.
    3.  Utwórz odwołanie do elementu stałotekstowego modelu danych **Kierunek**.

    [![kierunek\_tekstu stałego](./media/ger-power-bi-format-configuration-mapping-added-enum-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-added-enum.png)
5.  Wykonaj powiązanie elementów modelu danych **Intrastat** z elementami zaprojektowanego formatu, jak pokazano na poniższej ilustracji. [![Kończenie pracy wiązanie](./media/ger-power-bi-format-configuration-mapping-details-1024x454.png)](./media/ger-power-bi-format-configuration-mapping-details.png)

Po uruchomieniu format modułu ER wygeneruje dane wyjściowe w formacie programu Excel. Wyśle szczegóły transakcji Intrastat do danych wyjściowych i oddzieli je jako transakcje, które opisują działania importu lub eksportu. Kliknij **uruchomić** do testowania nowego formatu ER listy transakcji Intrastat na **Intrastat** stronę (**podatku**&gt;**deklaracje**&gt;**handlu zagranicznego**&gt;**Intrastat**). [![Intrastat strony](./media/ger-power-bi-format-test-run-transactions-1024x322.png)](./media/ger-power-bi-format-test-run-transactions.png) jest generowany następujący wynik danych wyjściowych. Plik nosi nazwę **Szczegóły importu i eksportu.xlsx**, jak określono w ustawieniach formatu. [![Importowanie i eksportowanie details.xlsx](./media/ger-power-bi-format-test-run-output-1024x472.png)](./media/ger-power-bi-format-test-run-output.png)

## <a name="configure-the-er-destination"></a>Konfigurowanie miejsca docelowego raportowania elektronicznego
Należy skonfigurować środowisko modułu ER do wysyłania danych wyjściowych nowej konfiguracji formatu ER w specjalny sposób.

-   Dane wyjściowe należy wysłać do folderu wybranego serwera programu SharePoint.
-   Każde wykonanie konfiguracji formatu musi tworzyć nową wersję tego samego pliku programu Excel.

Na **raportowania elektronicznego** stronę (**Administrowanie organizacją**&gt;**raportowania elektronicznego**), kliknij przycisk **miejsce docelowe raportowania elektronicznego** przedmiotu i dodać nowe miejsce docelowe. W polu **Odwołanie** zaznacz utworzoną wcześniej konfigurację formatu **Działania importu/eksportu**. Wykonaj następujące kroki, aby dodać nowy rekord plikowego miejsca docelowego dla odwołania.

1.  W polu **Nazwa** wprowadź tytuł plikowego miejsca docelowego.
2.  W polu **Nazwa pliku** wybierz nazwę **Plik wyjściowy programu Excel** dla składnika formatu pliku programu Excel.

Kliknij przycisk **Ustawienia** dla nowego rekordu miejsca docelowego. Następnie w oknie dialogowym **Ustawienia aplikacji docelowej** wykonaj następujące kroki.

1.  Na karcie **Power BI** w opcji **Włączone** ustaw wartość **Tak**.
2.  W polu **SharePoint** zaznacz utworzony wcześniej typu dokumentu **Współdzielony**.

## <a name="schedule-execution-of-the-configured-er-format"></a>Planowanie wykonywania skonfigurowanego formatu raportowania elektronicznego
Na **konfiguracje** stronę (**Administrowanie organizacją**&gt;**raportowania elektronicznego**&gt;**konfiguracje**), w drzewie konfiguracji wybierz **Import, Eksport działalności** konfiguracji, który został utworzony wcześniej. Zmień stan wersji 1.1 z **Robocza** na **Ukończono**, co spowoduje udostępnienie tego formatu do użytku. [![Konfiguracji na stronie](./media/ger-power-bi-format-configuration-complete-1024x401.png)](./media/ger-power-bi-format-configuration-complete.png) wybierz ukończoną wersję **Import / Eksport działalności** konfiguracji, a następnie kliknij **Uruchom**. Należy zwrócić uwagę, ze skonfigurowane miejsce docelowe będzie stosowane do danych wyjściowych wygenerowanych w formacie programu Excel. W opcji **Przetwarzanie wsadowe** ustaw wartość **Tak**, aby generować ten raport w trybie nienadzorowanym. Kliknij opcję **Cykl**, aby zaplanować wymagane cykliczne wykonywanie tego przetwarzania wsadowego. Cykl określa, jak często zaktualizowane dane będą przesyłane z programu Dynamics 365 for Operations do programu Power BI. [![Okno dialogowe Parametry raportu elektronicznego](./media/ger-power-bi-format-configuration-run-to-schedule-1024x413.png)](./media/ger-power-bi-format-configuration-run-to-schedule.png) po skonfigurowaniu, wykonanie zadania raportowania ER można znaleźć na **zadań wsadowych** stronę (**administrowania systemem &gt;zapytania &gt;zadań wsadowych**). [![Strona zadania wsadowego](./media/ger-power-bi-format-configuration-running-job-1024x410.png)](./media/ger-power-bi-format-configuration-running-job.png) po uruchomieniu tego zadania po raz pierwszy, miejsce docelowe tworzy nowy plik programu Excel, który ma skonfigurowanej nazwy zaznaczonego folderu programu SharePoint. Podczas każdego kolejnego wykonywania zadania aplikacja docelowa tworzy nową wersję tego pliku programu Excel. [![Nowa wersja pliku programu Excel](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2-1024x412.png)](./media/ger-power-bi-output-file-in-sharepoint-server-folder-2.png)

## <a name="create-a-power-bi-dataset-by-using-the-output-result-of-the-er-format"></a>Tworzenie zestawu danych programu Power BI za pomocą danych wyjściowych formatu raportowania elektronicznego
Zaloguj się w programie Power BI i otwórz istniejącą grupę (obszar roboczy) programu Power BI lub utwórz nową grupę. Albo kliknij **Dodaj** pod **pliki** w **importowanie lub łączenie z danymi** sekcji lub kliknij znak plus (**+**) obok **zestawów danych** w lewym okienku. [![Tworzenie zestawu danych](./media/ger-power-bi-add-dataset-1024x524.png)](./media/ger-power-bi-add-dataset.png) wybierz **programu SharePoint — witryny zespołu** opcji, a następnie wprowadź ścieżkę programu SharePoint Server, której używasz (**https://ax7partner.spoppe.com** w naszym przykładzie). Następnie przejdź do folderu **/Shared Documents/GER data/PowerBI** i wybierz utworzony plik programu Excel jako źródło danych dla nowego zestawu danych programu Power BI. [![Wybieranie pliku programu Excel](./media/ger-power-bi-add-dataset-select-excel-file-1024x522.png)](./media/ger-power-bi-add-dataset-select-excel-file.png) kliknij **Połącz**, a następnie kliknij przycisk **importowania**. Zostanie utworzony nowy zestaw danych oparty na wybranym pliku programu Excel. Zestaw danych może być również dodawany automatycznie do nowo tworzonego pulpitu nawigacyjnego. [![Zestaw danych na pulpicie nawigacyjnym](./media/ger-power-bi-added-dataset-1024x489.png)](./media/ger-power-bi-added-dataset.png) skonfigurować harmonogram odświeżania dla tego zestawu danych do wymuszenia aktualizacji okresowej. Okresowe aktualizacje umożliwiają wykorzystywanie nowych danych biznesowych pochodzących z programu Dynamics 365 for Operations poprzez okresowe generowanie raportu modułu ER przy użyciu nowych wersji pliku programu Excel, które są tworzone na serwerze programu SharePoint.

## <a name="create-a-power-bi-report-by-using-the-new-dataset"></a>Tworzenie raportu programu Power BI przy użyciu nowego zestawu danych
Aby wygenerować nowy raport programu Power BI, kliknij utworzony zestaw danych programu Power BI o nazwie **Szczegóły importu i eksportu**. Następnie skonfiguruj wizualizację. Na przykład zaznacz wizualizację **Wypełniona mapa** i skonfiguruj ją w następujący sposób:

-   Przypisz pole **CountryOrigin** zestawu danych do pola **Lokalizacja** w wizualizacji mapy.
-   Przypisz pole **Kwota** zestawu danych do pola **Nasycenie kolorów** w wizualizacji mapy.
-   Dodaj pola **Działanie** i **Rok** zestawu danych do kolekcji pól **Filtry** w wizualizacji mapy.

Zapisz raport programu Power BI pod nazwą **Raport o szczegółach importu i eksportu**. [![Importowanie i eksportowanie raportu szczegółów](./media/ger-power-bi-added-report-1024x498.png)](./media/ger-power-bi-added-report.png) należy zauważyć, że mapa przedstawia krajach/regionach, które są wymienione w pliku programu Excel (Austria i Szwajcaria w tym przykładzie). Te kraje/regiony są pokolorowane w celu pokazania proporcji kwot zafakturowanych dla każdego z nich. Zaktualizuj listę transakcji Intrastat. Zostanie dodana transakcja eksportu pochodząca z Włoch. [![Lista transakcji Intrastat](./media/ger-power-bi-new-run-new-transaction-1024x321.png)](./media/ger-power-bi-new-run-new-transaction.png) czekać na wykonanie następnego zaplanowanego raportu ER i następnej zaplanowanej aktualizacji zestawu danych BI zasilania. Następnie przejrzyj raport programu Power BI (zaznacz opcję wyświetlania tylko transakcji importu). Zaktualizowana mapa pokazuje obecnie Włochy. [![Zaktualizowane mapy](./media/ger-power-bi-new-run-new-map-1024x511.png)](./media/ger-power-bi-new-run-new-map.png)

## <a name="access-power-bi-report-in-dynamics-365-for-operations"></a>Przechodzenie do raportu programu Power BI w programie Dynamics 365 for Operations
Skonfiguruj integrację między programami Dynamics 365 for Operations i Power BI. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji Power BI dla przestrzeni roboczych](configure-power-bi-integration.md). Na **raportowania elektronicznego** strony obszar roboczy, który obsługuje integrację Power BI (**Administrowanie organizacją**&gt;**obszary robocze**&gt;**obszaru roboczego raportowania elektronicznego**), kliknij przycisk **opcje**&gt;**Otwórz raport katalog**. Zaznacz utworzony raport programu Power BI zatytułowany **Szczegóły importu i eksportu**, a zostanie on wyświetlony jako element akcji na wybranej stronie. Kliknij element akcji, a zostanie otwarta strona programu Dynamics 365 for Operations pokazująca raport zaprojektowany w programie Power BI. [![Importowanie i eksportowanie raportu szczegółów](./media/ger-power-bi-review-bi-report-in-ax-form-1024x586.png)](./media/ger-power-bi-review-bi-report-in-ax-form.png)

<a name="see-also"></a>Informacje dodatkowe
--------

[Miejsca docelowe raportowania elektronicznego](electronic-reporting-destinations.md)

[Raportowanie elektroniczne — omówienie](general-electronic-reporting.md)


