---
title: Przekazywanie konfiguracji do usługi Lifecycle Services
description: Ten temat wyjaśnia sposób tworzenia nowej konfiguracji modułu Raportowanie elektroniczne (ER) i przekazywania jej do usług Microsoft Dynamics Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 09/14/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 92fc6d7a8b2508c9a1f7b56ca8115adbd6ae00ea
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092548"
---
# <a name="upload-a-configuration-into-lifecycle-services"></a>Przekazywanie konfiguracji do usługi Lifecycle Services

[!include [banner](../../includes/banner.md)]

Ten temat wyjaśnia, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfigurację [raportowania elektronicznego (ER)](../general-electronic-reporting.md#Configuration) i przekazać ją do [biblioteki zasobów na poziomie projektu](../../lifecycle-services/asset-library.md) w Microsoft Dynamics Lifecycle Services (LCS).

W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. i przekażesz ją do usługi LCS. Podane kroki można ukończyć dla dowolnej firmy, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki w temacie [Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywne](er-configuration-provider-mark-it-active-2016-11.md). Wymagany jest również dostęp do usługi LCS.

1. Zaloguj się do aplikacji przy użyciu jednej z następujących ról:

    - Deweloper raportowania elektronicznego
    - Administrator systemu

2. Wybierz kolejno opcje **Administrowanie organizacją** \> **Obszary robocze** \> **Raportowanie elektroniczne**.
3. Wybierz firmę **Litware, Inc.**” i ustaw ją jako **aktywną**.
4. Wybierz **Konfiguracje**.

<a name="accessconditions"></a>
> [!NOTE]
> Upewnij się, że bieżący użytkownik Dynamics 365 Finance jest członkiem projektu usługi LCS zawierającego [bibliotekę elementów zawartości](../../lifecycle-services/asset-library.md#asset-library-support), która jest używana do importowania konfiguracji ER.
>
> Nie można uzyskać dostępu do projektu LCS z poziomu repozytorium ER, które reprezentuje domenę inną niż domena używana w Finance. Jeśli zostanie podjęta taka próba, zostanie wyświetlona pusta lista projektów LCS i nie będzie można importować konfiguracji ER z biblioteki elementów zawartości na poziomie projektu w usłudze LCS. Aby uzyskać dostęp do bibliotek elementów zawartości na poziomie projektu z repozytorium ER używanego do importowania konfiguracji ER, należy zalogować się do Finance przy użyciu poświadczeń użytkownika, który należy do dzierżawy (domeny), dla którego została zainicjowana bieżąca instancja Finance.

## <a name="create-a-new-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Wybierz przycisk **Utwórz konfigurację** na stronie **konfiguracje**, aby otworzyć rozwijane okno dialogowe.

    W tym przykładzie utworzysz konfigurację, która zawiera przykładowy model danych dla dokumentów elektronicznych. Ta konfiguracja modelu danych zostanie później przekazana do usługi LCS.

3. W polu **Nazwa** wpisz **Konfiguracja przykładowego modelu**.
4. W polu **Opis** wpisz **Konfiguracja przykładowego modelu**.
5. Wybierz **Utwórz konfigurację**.
6. Wybierz **Projektanta modelu**.
7. Wybierz pozycję **Nowy**.
8. W polu **Nazwa** wpisz **Punkt wejścia**.
9. Wybierz opcję **Dodaj**.
10. Wybierz opcję **Zapisz**.
11. Zamknij stronę.
12. Wybierz opcję **Zmień stan**.
13. Wybierz opcję **Zakończone**.
14. Kliknij przycisk **OK**.
15. Zamknij stronę.

## <a name="register-a-new-repository"></a>Rejestrowanie nowego repozytorium

1. Wybierz kolejno opcje **Administrowanie organizacją \> Obszary robocze \> Raportowanie elektroniczne**.

2. W obszarze **Dostawcy konfiguracji** wybierz kafelek **Litware, Inc.**.

3. Na kafelku **Litware, Inc.** wybierz **Repozytoria**.

    Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.

4. Wybierz przycisk **Dodaj**, aby otworzyć rozwijane okno dialogowe.

    Teraz można dodać nowe repozytorium.

5. W polu **Typ repozytorium konfiguracji** wpisz **LCS**.
6. Kliknij opcję **Utwórz repozytorium**.
7. W polu **Projekt** wprowadź lub wybierz wartość.

    W tym przykładzie wybierz projekt LCS. Trzeba mieć [dostęp](#accessconditions) do projektu.

8. Kliknij przycisk **OK**.

    Wypełnij wpis nowego repozytorium.

9. Na liście oznacz wybrany wiersz.

    W tym przykładzie wybierz rekord repozytorium **LCS**.

    Należy zauważyć, że zarejestrowane repozytorium jest oznaczone przez bieżącego dostawcę. Innymi słowy, tylko konfiguracje należące do tego dostawcy mogą być umieszczane w tym repozytorium i w związku z tym przekazywane do wybranego projektu usługi LCS.

10. Kliknij przycisk **Otwórz**.

    Otwórz repozytorium, aby wyświetlić listę konfiguracji raportowania elektronicznego. Lista będzie pusta, jeśli ten projekt nie był jeszcze używany w udostępnianiu konfiguracji raportowania elektronicznego.

11. Zamknij stronę.
12. Zamknij stronę.

## <a name="upload-a-configuration-into-lcs"></a>Przesyłanie konfiguracji do usługi LCS

1. Przejdź do opcji **Administrowanie organizacją \> Raporty elektroniczne \> Konfiguracje**.
2. Na stronie **Konfiguracje** w drzewie konfiguracji wybierz pozycję **Przykładowy model konfiguracji**.

    Musisz zaznaczyć utworzone konfiguracje, które zostały już ukończone.

3. Na liście znajdź i zaznacz odpowiedni rekord.

    W tym przykładzie zaznacz wersję wybranej konfiguracji ze stanem **Zakończono**.

4. Wybierz opcję **Zmień stan**.
5. Wybierz opcję **Udostępnij**.

    Stan konfiguracji zmienia się z **Zakończono** na **Współużytkowana** gdy konfiguracja jest opublikowana w usłudze LCS.

6. Kliknij przycisk **OK**.
7. Na liście znajdź i zaznacz odpowiedni rekord.

    W tym przykładzie zaznacz wersję tej konfiguracji mającą stan **Udostępniono**.

    Należy zauważyć, że stan wybranej wersji został zmieniony z **Zakończono** na **Udostępniono**.

8. Zamknij stronę.
9. Wybierz **Repozytoria**.

    Teraz można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.

10. Kliknij przycisk **Otwórz**.

    W tym przykładzie wybierz rekord repozytorium **LCS** i otwórz je.

    Należy zwrócić uwagę, że wybrana konfiguracja jest wyświetlana jako element zawartości wybranego projektu usługi LCS.

11. Otwórz LCS, przechodząc na <https://lcs.dynamics.com>.
12. Otwórz projekt, który został użyty wcześniej do rejestracji repozytorium.
13. Otwórz bibliotekę elementów zawartości projektu.
14. Wybierz typ elementu **Konfiguracja GER**.

    Przekazana konfiguracja ER powinna zostać wyświetlona na liście.

    Należy zauważyć, że przekazaną konfigurację usługi LCS można zaimportować do innego wystąpienia, jeśli dostawcy mają dostęp do tego projektu usługi LCS.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]