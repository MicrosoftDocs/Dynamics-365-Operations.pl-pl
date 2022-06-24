---
title: Udostępnianie konfiguracji ER w oprogramowaniu RCS/repozytorium globalnym organizacjom zewnętrznym
description: W tym artykule objaśniono sposób udostępniania konfiguracji Raportowania elektronicznego (ER) w usługach Microsoft Regulatory Configuration Services (RCS)/repozytorium globalnym bezpośrednio organizacjom zewnętrznym.
author: JaneA07
ms.date: 05/04/2020
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
ms.openlocfilehash: 976a86aee75581d1afa764bea049b6c0eaecf9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888931"
---
# <a name="share-electronic-reporting-er-configurations-in-regulatory-configuration-services-rcs-global-repository-with-external-organizations"></a>Udostępnianie konfiguracji Raportowania elektronicznego (ER) w repozytorium globalnym usług Microsoft Regulatory Configuration Services (RCS)organizacjom zewnętrznym

[!include [banner](../includes/banner.md)]

Do udostępniania konfiguracji Raportowania elektronicznego (ER) można używać usług Regulatory Configuration Services (RCS) firmy Microsoft, a następnie publikować je dla organizacji zewnętrznych.

Poniższe procedury opisują sposób, w jaki użytkownik RCS może udostępniać wersję konfiguracji ER, która została skonfigurowana w wystąpieniu usług RCS przy użyciu organizacji zewnętrznej. Przed wykonaniem tych procedur należy najpierw spełnić następujące warunki wstępne:

- Uzyskanie dostępu do wystąpienia usług RCS.
- Utworzenie aktywnego dostawcy konfiguracji. Dalsze informacje znajdują się w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
- Utworzenie i przekazanie nowej wersji konfiguracji ER. Aby uzyskać więcej informacji, zobacz temat [Tworzenie i przekazywanie nowej wersji konfiguracji Raportowania elektronicznego (ER)](rcs-global-repo-upload.md).

Należy również upewnić się, że dla firmy aprowizowano środowisko RCS.

1. W module Finanse i Operacje przejdź do opcji **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
2. Jeśli w firmie nie aprowizowano środowiska RCS, wybierz pozycję zewnętrzną **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu aprowizowania środowiska RCS.

Jeśli już aprowizowano środowisko RCS, należy skorzystać z adresu URL strony, aby uzyskać do niego dostęp, wybierając opcję logowania.

## <a name="verify-the-configuration-that-you-want-to-share"></a>Weryfikowanie konfiguracji do udostępnienia

Wykonaj poniższe kroki, aby sprawdzić, czy konfiguracja, którą chcesz udostępnić, została już przekazana do repozytorium globalnego.

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Repozytoria** dla dostawcy konfiguracji.

    ![Dostawcy konfiguracji.](media/1_RCS_Repo_for_config_provider.JPG)

2. Wybierz pozycję **Repozytorium globalne** \> **Otwórz**.
3. Wyszukaj konfigurację do udostępnienia. Możesz użyć pola filtru, aby zawęzić wyszukiwanie. Jeśli nie możesz znaleźć konfiguracji w repozytorium globalnym, postępuj zgodnie z instrukcjami w temacie [Tworzenie i przekazywanie nowej wersji konfiguracji Raportowania elektronicznego (ER)](rcs-global-repo-upload.md).

## <a name="share-er-configurations-with-external-organizations"></a>Udostępnianie konfiguracji ER organizacjom zewnętrznym

Po utworzeniu konfiguracji w ramach dostawcy konfiguracji można udostępnić ją bezpośrednio organizacjom zewnętrznym, korzystając ze skróconej karty **Udostępnione** na stronie **globalnego repozytorium konfiguracji**.

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz pozycję **Repozytoria** dla dostawcy konfiguracji.
2. Wybierz pozycję **Repozytorium globalne** \> **Otwórz**. 
3. Wybierz konfigurację do udostępnienia.
4. Na skróconej karcie **Udostępnione** wybierz pozycję **Organizacje**.

    ![Skrócona karta Udostępnione.](media/1_RCS_Repo_for_Share_with_org.JPG)

5. W oknie dialogowym wprowadź nazwę domeny dla organizacji zewnętrznej, a następnie kliknij przycisk **OK**.

    ![Okno dialogowe udostępniania wersji konfiguracji organizacji zewnętrznej.](media/1_RCS_Repo_for_Share_with_form.JPG)

Konfiguracja jest udostępniana organizacji zewnętrznej i jest dostępna dla tej organizacji w repozytorium globalnym. Z tego miejsca można ją zaimportować do wystąpienia usług RCS organizacji lub do jej wystąpień aplikacji finansowych i operacyjnych.

6. Aby cofnąć udostępnianie konfiguracji poprzednio udostępnionej organizacji zewnętrznej, wybierz konfigurację i kliknij pozycję **Anuluj udostępnianie**, a następnie wybierz przycisk **OK**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]