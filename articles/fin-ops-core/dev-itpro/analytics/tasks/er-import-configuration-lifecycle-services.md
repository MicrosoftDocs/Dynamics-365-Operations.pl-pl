---
title: Importowanie konfiguracji z usługi Lifecycle Services
description: W tym temacie opisano sposób importowania nowej wersji konfiguracji raportowania elektronicznego z usług Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 602886b0dd729b8ec52940f42bd1c393dac8acda
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093702"
---
# <a name="import-a-configuration-from-lifecycle-services"></a>Importowanie konfiguracji z usługi Lifecycle Services

[!include [banner](../../includes/banner.md)]

Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji [raportowania elektronicznego (ER)](../general-electronic-reporting.md#Configuration) z [biblioteki zasobów na poziomie projektu](../../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (LCS).

W tym przykładzie wybierzesz żądaną wersję konfiguracji raportowania elektronicznego dla przykładowej firmy Litware, Inc. i zaimportujesz ją. Podane kroki można wykonać dla dowolnej firmy, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). Wymagany jest również dostęp do usługi LCS.

1. Zaloguj się do aplikacji przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. Wybierz **Konfiguracje**.

<a name="accessconditions"></a>
> [!NOTE]
> Upewnij się, że bieżący użytkownik Dynamics 365 Finance jest członkiem projektu usługi LCS zawierającego [dostęp](../../lifecycle-services/asset-library.md#asset-library-support) do biblioteki elementów zawartości, do której użytkownik chce uzyskać dostęp na potrzeby importowania konfiguracji ER.
>
> Nie można uzyskać dostępu do projektu LCS z poziomu repozytorium ER, które reprezentuje domenę inną niż domena używana w Finance. Jeśli zostanie podjęta taka próba, zostanie wyświetlona pusta lista projektów LCS i nie będzie można importować konfiguracji ER z biblioteki elementów zawartości na poziomie projektu w usłudze LCS. Aby uzyskać dostęp do bibliotek elementów zawartości na poziomie projektu z repozytorium ER używanego do importowania konfiguracji ER, należy zalogować się do Finance przy użyciu poświadczeń użytkownika, który należy do dzierżawy (domeny), dla którego została zainicjowana bieżąca instancja Finance.

## <a name="delete-a-shared-version-of-a-data-model-configuration"></a>Usuwanie udostępnionej wersji konfiguracji modelu danych

1. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Przykładowy model konfiguracji**.

    Utworzona pierwsza wersja konfiguracji przykładowego modelu danych została utworzona i opublikowana w usłudze LCS podczas procedury [Przekazywanie konfiguracji ER do usługi Lifecycle Services](er-upload-configuration-into-lifecycle-services.md). W tej procedurze usuniesz tę wersję konfiguracji raportowania elektronicznego. Następnie ta wersja zostanie zaimportowana z usługi LCS w dalszej części tego tematu.

2. Na liście znajdź i zaznacz odpowiedni rekord.

    W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**. Ten stan wskazuje, że konfiguracja została opublikowana w usłudze LCS.

3. Wybierz opcję **Zmień stan**.
4. Kliknij przycisk **Wycofaj**.

    Zmieniając stan wybranej wersji z **Udostępniono** na **Wycofano**, wersja staje się możliwa usunięcia.

5. Kliknij przycisk **OK**.
6. Na liście znajdź i zaznacz odpowiedni rekord.

    W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Wycofano**.

7. Wybierz opcję **Usuń**.
8. Wybierz opcję **Tak**.

    Należy zauważyć, że teraz jest dostępna tylko wersja robocza 2 wybranej konfiguracji przykładowego modelu danych.

9. Zamknij stronę.

## <a name="import-a-shared-version-of-a-data-model-configuration-from-lcs"></a>Importowanie udostępnionej wersji konfiguracji modelu danych z usługi LCS

1. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.

2. W obszarze **Dostawcy konfiguracji** wybierz kafelek **Litware, Inc.**.

3. Na kafelku **Litware, Inc.** wybierz **Repozytoria**.

    Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.

4. Kliknij przycisk **Otwórz**.

    W tym przykładzie wybierz rekord repozytorium **LCS** i otwórz je. Musisz mieć [dostęp](#accessconditions) do projektu usługi LCS i do biblioteki elementów zawartości, do której ma dostęp wybrane repozytorium ER.

5. Na liście oznacz wybrany wiersz.

    Na potrzeby tego przykładu, na liście wersji zaznacz pierwszą wersję **konfiguracji przykładowego modelu**.

6. Wybierz opcję **Importuj**.
7. Potwierdź import wybranej wersji z usługi LCS klikając **Tak**.

    Komunikat informacyjny potwierdza, że wybrana wersja została pomyślnie zaimportowana.

8. Zamknij stronę.
9. Zamknij stronę.
10. Wybierz **Konfiguracje**.
11. W drzewie zaznacz element **Konfiguracja przykładowego modelu**.
12. Na liście znajdź i zaznacz odpowiedni rekord.

    W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.

    Należy zauważyć, że teraz jest również dostępna udostępniona wersja 1 wybranej konfiguracji przykładowego modelu danych.
