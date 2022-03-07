---
title: Tworzenie konfiguracji raportowania elektronicznego w RCS i przekazywanie ich do repozytorium globalnego
description: W tym temacie objaśniono sposób tworzenia konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS) i przekazywania jej do repozytorium globalnego.
author: JaneA07
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: eb04362d6d7261af56d2940b085fbc8d43c9d662
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2022
ms.locfileid: "7965096"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Tworzenie konfiguracji raportowania elektronicznego w usługach Regulatory Configuration Services (RCS) i przekazywanie ich do repozytorium globalnego

[!include [banner](../includes/banner.md)]

Do projektowania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je, aby umożliwić ich używanie w organizacji.

W poniższych procedurach opisano, jak użytkownik w roli administratora systemu lub dewelopera Raportowania elektronicznego może utworzyć pochodną wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS, a następnie przekazać pochodną konfigurację do repozytorium globalnego. 

Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:

- Masz dostęp do środowiska z RCS dla swojej organizacji.
- Utwórz aktywnego dostawcę konfiguracji i uaktywnij go. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Musisz upewnić się, że środowisko RCS jest aprowizowane dla Twojej organizacji. Jeśli dla organizacji nie jest autoryzowane wystąpienie usługi RCS, można wykonać następujące czynności:

1. W module Finanse i Operacje przejdź do opcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. W **powiązanych łączach/łączach zewnętrznych** wybierz opcję **Regulatory services — Konfiguracja**, a następnie postępuj zgodnie z instrukcjami, aby **zarejestrować się**, aby je skonfigurować.

Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję **logowania**.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Tworzenie wersji pochodnej konfiguracji w usługach RCS

> [!NOTE]
> Jeśli jest to pierwszy raz, w których były używane pliki RCS, nie będzie dostępna konfiguracja, z której będzie można korzystać. Konieczne będzie zaimportowanie konfiguracji z repozytorium globalnym. Więcej informacji można znaleźć w temacie [Pobieranie konfiguracji ER z globalnego repozytorium usługi Configuration service](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

1. **Zaloguj się** do RCS wybierz kafelek roboczy **Raportowanie elektroniczne**.
2. Sprawdź, czy masz aktywnego dostawcę konfiguracji dla swojej organizacji, który jest ustawiony jako aktywny (zobacz wymagania wstępne). 
3. Wybierz **Raportowanie konfiguracji**.
4. Wybierz konfigurację, z której chcesz uzyskać nową wersję. Możesz użyć pola filtru nad drzewem, aby zawęzić wyszukiwanie.
5. Wybierz pozycję **Utwórz konfigurację** \> **Pochodzi od nazwy**.
6. Wprowadź nazwę i opis, a następnie wybierz opcję **Utwórz konfigurację**, aby utworzyć nową wersję pochodną ze stanem „Szkic”.
7. W razie potrzeby wybierz nową konfigurację pochodną i w razie potrzeby dokonaj dodatkowych zmian w formacie konfiguracji. 
8. Po zakończeniu zmian należy ustawić dla konfiguracji **Zmień stan** na **Zakończono**, aby było możliwe opublikowanie go w repozytorium. Kliknij przycisk **OK**.

![Nowa wersja konfiguracji w usługach RCS.](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Po zmianie stanu konfiguracji może pojawić się komunikat o błędzie weryfikacji, który jest związany z dołączonymi aplikacjami. Aby wyłączyć weryfikowanie, w okienku akcji na karcie **Konfiguracje** wybierz pozycję **Parametry użytkownika**, a następnie ustaw opcję **Pomiń weryfikację przy zmianie stanu konfiguracji i zmianie bazy** na **Tak** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Przekazywanie konfiguracji do repozytorium globalnego

Aby udostępnić nową lub pochodną konfigurację swojej organizacji, możesz przesłać ją do globalnego repozytorium, wykonując następujące kroki:

1. Wybierz zakończoną wersję konfiguracji, a następnie wybierz pozycję **Przekaż do repozytorium**.
2. Wybierz opcję **Globalne (Microsoft)**, a następnie wybierz pozycję **Przekaż**.

    ![Opcje przekazywania do repozytorium.](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**. 
4. W razie potrzeby zaktualizuj opis wersji, a następnie wybierz przycisk **OK**. Opcjonalnie można przekazać wersję do połączonej aplikacji lub do repozytorium GIM.  

Stan konfiguracji jest aktualizowany do wartości **Udostępnione**, a konfiguracja jest przekazywana do repozytorium globalnego. Zostanie również utworzona wersja robocza przekazanej konfiguracji i może zostać użyta, jeśli będą wymagane kolejne zmiany.

Po przekazać konfigurację do repozytorium globalnego można pracować z nim w następujący sposób:

- Zaimportuj ją do wystąpienia rozwiązania Dynamics 365. Aby uzyskać więcej informacji, zobacz temat [(ER) Importowanie konfiguracji z usług RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Udostępnij ją firmie lub organizacji zewnętrznej, zobacz temat [RCS — udostępnianie konfiguracji Raportowania elektronicznego (ER) organizacjom zewnętrznymi](rcs-global-repo-share-configuration.md)

    ![Wersja konfiguracji pochodnej Intrastat Contoso w repozytorium globalnym.](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Usuwanie konfiguracji z repozytorium globalnego
Wykonaj następujące kroki, aby usunąć konfigurację utworzoną przez organizację.

1. W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy dostawca konfiguracji jest **Aktywny**. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Na aktywnym dostawcy konfiguracji wybierz pozycję **repozytorium**.
3. Wybierz typ repozytorium **Globalne** i wybierz opcję **Otwórz**.
4. Na skróconej karcie **Filtr** znajdź konfigurację, którą chcesz usunąć, przy użyciu funkcji **Filtrowania**.
5. W na skróconej karcie **Wersja** wybierz wersję konfiguracji, którą chcesz usunąć, a następnie wybierz opcję **Usuń**:

    ![Usuwanie konfiguracji z repozytorium globalnego.](media/RCS_Delete_from_GlobalRepo.JPG)

6. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.

    ![Komunikat potwierdzający usunięcie wersji konfiguracji.](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Wersja konfiguracji zostanie usunięta i zostanie wyświetlony komunikat z potwierdzeniem. 

> [!NOTE]
> Konfiguracje mogą być usuwane tylko przez dostawcę konfiguracji, który je utworzył. Jeśli konfiguracja została udostępniona innej organizacji, przed jej usunięciem należy cofnąć udostępnianie.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
