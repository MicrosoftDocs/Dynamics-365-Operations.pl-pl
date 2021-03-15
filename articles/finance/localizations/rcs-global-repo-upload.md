---
title: Tworzenie konfiguracji raportowania elektronicznego w RCS i przekazywanie ich do repozytorium globalnego
description: W tym temacie objaśniono sposób tworzenia konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS) i przekazywania jej do repozytorium globalnego.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: ef12c911c8953b181db1c0eff0874a3d8cfcb3da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005755"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Tworzenie konfiguracji raportowania elektronicznego w usługach Regulatory Configuration Services (RCS) i przekazywanie ich do repozytorium globalnego

[!include [banner](../includes/banner.md)]

Do projektowania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je, aby umożliwić ich używanie w organizacji.

W poniższych procedurach opisano, jak użytkownik w roli administratora systemu lub dewelopera Raportowania elektronicznego może utworzyć pochodną wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS, a następnie przekazać pochodną konfigurację do repozytorium globalnego. 

Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:

- Uzyskanie dostępu do wystąpienia usług RCS.
- Utworzenie aktywnego dostawcy konfiguracji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

Należy również upewnić się, że dla firmy aprowizowano środowisko RCS.

1. W aplikacji Finance and Operations przejdź do obszaru **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję zewnętrzną **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.

Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję logowania.

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>Tworzenie wersji pochodnej konfiguracji w usługach RCS

1. W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy masz aktywnego dostawcę konfiguracji dla organizacji. 
2. Wybierz **Raportowanie konfiguracji**.
3. Wybierz konfigurację, z której chcesz uzyskać nową wersję. Możesz użyć pola filtru nad drzewem, aby zawęzić wyszukiwanie.
4. Wybierz pozycję **Utwórz konfigurację** \> **Pochodzi od nazwy**.
5. Wprowadź nazwę i opis, a następnie wybierz opcję **Utwórz konfigurację**, aby utworzyć nową wersję pochodną.
6. Wybierz nową konfigurację pochodną, dodaj opis wersji, a następnie wybierz przycisk **OK**. Stan konfiguracji zostanie zmieniony na **Zakończono**.

![Nowa wersja konfiguracji w usługach RCS](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> Po zmianie stanu konfiguracji może pojawić się komunikat o błędzie weryfikacji, który jest związany z dołączonymi aplikacjami. Aby wyłączyć weryfikowanie, w okienku akcji na karcie **Konfiguracje** wybierz pozycję **Parametry użytkownika**, a następnie ustaw opcję **Pomiń weryfikację przy zmianie stanu konfiguracji i zmianie bazy** na **Tak** 

## <a name="upload-a-configuration-to-the-global-repository"></a>Przekazywanie konfiguracji do repozytorium globalnego

Aby udostępnić organizacji nową lub pochodną konfigurację, można ją przekazać do repozytorium globalnego.

1. Wybierz zakończoną wersję konfiguracji, a następnie wybierz pozycję **Przekaż do repozytorium**.
2. Wybierz opcję **Globalne (Microsoft)**, a następnie wybierz pozycję **Przekaż**.

    ![Opcje przekazywania do repozytorium](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**. 
4. W razie potrzeby zaktualizuj opis wersji, a następnie wybierz przycisk **OK**. 

Stan konfiguracji jest aktualizowany do wartości **Udostępnij**, a konfiguracja jest przekazywana do repozytorium globalnego. W tym miejscu można pracować w następujący sposób:

- Zaimportuj ją do wystąpienia rozwiązania Dynamics 365. Aby uzyskać więcej informacji, zobacz temat [(ER) Importowanie konfiguracji z usług RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).
- Udostępnij ją firmie lub organizacji zewnętrznej, zobacz temat [RCS — udostępnianie konfiguracji Raportowania elektronicznego (ER) organizacjom zewnętrznymi](rcs-global-repo-share-configuration.md)

    ![Wersja konfiguracji pochodnej Intrastat Contoso w repozytorium globalnym](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a>Usuwanie konfiguracji z repozytorium globalnego
Wykonaj następujące kroki, aby usunąć konfigurację utworzoną przez organizację.

1. W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy dostawca konfiguracji jest **Aktywny**. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
2. Na aktywnym dostawcy konfiguracji wybierz pozycję **repozytorium**.
3. Wybierz typ repozytorium **Globalne** i wybierz opcję **Otwórz**.
4. Na skróconej karcie **Filtr** znajdź konfigurację, którą chcesz usunąć, przy użyciu funkcji **Filtrowania**.
5. W na skróconej karcie **Wersja** wybierz wersję konfiguracji, którą chcesz usunąć, a następnie wybierz opcję **Usuń**:

    ![Usuwanie konfiguracji z repozytorium globalnego](media/RCS_Delete_from_GlobalRepo.JPG)

6. W wyświetlonym oknie wiadomości z potwierdzeniem wybierz przycisk **Tak**.

    ![Komunikat potwierdzający usunięcie wersji konfiguracji](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
Wersja konfiguracji zostanie usunięta i zostanie wyświetlony komunikat z potwierdzeniem. 

> [!NOTE]
> Konfiguracje mogą być usuwane tylko przez dostawcę konfiguracji, który je utworzył. Jeśli konfiguracja została udostępniona innej organizacji, przed jej usunięciem należy cofnąć udostępnianie.
 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]