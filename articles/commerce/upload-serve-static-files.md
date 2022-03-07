---
title: Przekazywanie i obsługiwanie plików statycznych
description: W tym temacie opisano sposób przekazywania pliku statycznego do kreatora witryn Microsoft Dynamics 365 Commerce oraz tworzenia niestandardowego adresu URL i nazwy pliku, które mogą być używane do żądania tego pliku.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 389d33189644241dcf98da0c7f3b841e82a4430ac459dc8027284cecc299b4b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714690"
---
# <a name="upload-and-serve-static-files"></a>Przekazywanie i obsługiwanie plików statycznych

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób przekazywania pliku statycznego do kreatora witryn Microsoft Dynamics 365 Commerce oraz tworzenia niestandardowego adresu URL i nazwy pliku, które mogą być używane do żądania tego pliku.

Niektóre łączniki innych firm wymagają, aby plik był hostowany i obsługiwany przez witrynę handlu elektronicznego. Te łączniki oczekują, że plik będzie zwracany przez żądania do konkretnej ścieżki URL wywołania zwrotnego i nazwy pliku. W tym temacie opisano sposób przekazywania i obsługiwania pliku statycznego, który ma definiowany przez użytkownika adres URL i nazwę pliku w witrynie handlu elektronicznego Dynamics 365 Commerce.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Utwórz adres URL witryny, który zwraca plik statyczny

Aby utworzyć adres URL witryny, który zwraca plik statyczny w kreatorze witryny Commerce, wykonaj następujące kroki.

1. Przejdź do biblioteki multimediów w witrynie i przekaż plik, który powinien być obsługiwany przez żądania kierowane do zdefiniowanego adresu URL. Jeśli plik został już przekazany, można pominąć ten krok.
1. Przejdź do **adresów URL** witryny.
1. Wybierz pozycję **Nowy \> Nowy adres URL**.
1. W oknie dialogowym **Nowy adres URL** wybierz opcję **Zasób biblioteki multimediów**.
1. W polu **Ścieżka URL** wprowadź ścieżkę URL. Umożliwia uwzględnienie nazwy pliku w ścieżce.
1. Wybierz pozycję **Następny**. Biblioteka multimediów jest otwarta i zawiera wszystkie zasoby multimedialne typu **dokument**, które zostały przekazane.
1. Wybierz plik, który ma być obsługiwany dla żądań dla adresu URL zdefiniowanego w kroku 5.
1. Wybierz opcję **Zapisz**.

W tym momencie utworzony adres URL jest w stanie wersji roboczej. Plik, do którego wskazuje adres URL, nie zostanie zwrócony do momentu opublikowania adresu URL. Przed opublikowaniem adresu URL można sprawdzić, czy zwróci on poprawne dane.

## <a name="validate-and-publish-a-url"></a>Weryfikowanie i publikowanie adresu URL

Aby zweryfikować adres URL przed jego opublikowaniem, wykonaj następujące kroki.

1. Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do podglądu.
2. W okienku właściwości po prawej stronie, pod przyciskiem **Edycja**, zaznacz odpowiednie łącze URL. Zostanie otwarte nowe okno przeglądarki i pojawi się komunikat o błędzie 404.
3. W adresie URL należy dołączyć ciąg kwerendy w postaci **?preview=inprogress** (na przykład `https://yoursite.com/callback.html?preview=inprogress`), a następnie ponownie załadować stronę. Plik przekazany do biblioteki multimediów powinien zostać zwrócony w odpowiedzi.

Po sprawdzeniu adresu URL można go opublikować.

1. Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL.
2. Na pasku poleceń wybierz opcję **Publikuj**.

## <a name="update-the-file-that-a-url-points-to"></a>Aktualizacja pliku, na który wskazuje adres URL

Po opublikowaniu adresu URL można go aktualizować w taki sposób, aby wskazywał inny plik. Można również zaktualizować adres URL, tak aby wskazywał inny typ zasobu, zgodnie z opisem w następnej sekcji. Można na przykład wskazać adres URL na stronie wewnętrznej lub przekierowaniu.

Aby zaktualizować plik, na który wskazuje adres URL, wykonaj następujące kroki.

1. Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do aktualizacji.
1. W panelu właściwości po prawej stronie wybierz pozycję **Edytuj**.
1. W obszarze **Przypisywanie adresów URL** zaznacz pole **Krok 2**, a następnie wybierz nowy dokument z biblioteki multimediów.
1. Wybierz opcję **Zastosuj**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Aktualizacja typu zasobu, na który wskazuje adres URL

Można również zaktualizować adres URL, aby wskazywał na inny typ elementu zawartości (zasobu), taki jak wewnętrzna strona lub przekierowanie.

Aby zaktualizować typ zasobu, na który wskazuje adres URL, wykonaj następujące kroki.

1. Przejdź do **Adresów URL** swojego serwisu i wybierz adres URL do aktualizacji.
1. W panelu właściwości po prawej stronie wybierz pozycję **Edytuj**.
1. W obszarze **Przypisywanie adresu URL** w **Kroku 1** wybierz inny typ zasobu.
1. Zaznacz pole **Krok 2**, a następnie wybierz nowy zasób.
1. Wybierz opcję **Zastosuj**.

## <a name="change-the-url-path"></a>Zmiana ścieżki URL

Po utworzeniu adresu URL nie można zmienić jego ścieżki. Jeśli trzeba zmienić ścieżkę URL, która obsługuje plik lub jakikolwiek inny typu zasobu, należy utworzyć nowy adres URL, zmapować go do istniejącego pliku lub innego zasobu, a następnie cofnąć publikowanie i usunąć stary adres URL.

Aby zmienić ścieżkę adresu URL, wykonaj następujące kroki.

1. Aby utworzyć nowy adres URL i zmapować go do istniejącego pliku lub innego zasobu, postępuj zgodnie z instrukcjami w sekcji [Tworzenie adresu URL witryny, który zwraca plik statyczny](#create-a-site-url-that-returns-a-static-file), dostępnej powyżej w tym temacie.
1. Wybierz nowy adres URL i wybierz opcję **Publikuj** na pasku poleceń. Nowy adres URL zostanie opublikowany.
1. Aby cofnąć publikowanie starego adresu URL, zaznacz go, a następnie wybierz opcję **Cofnij publikowanie** na pasku poleceń. W razie potrzeby można teraz usunąć stary adres URL.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania cyfrowymi składnikami majątku](dam-overview.md)

[Przekazanie obrazów](dam-upload-images.md)

[Przekaż pliki wideo](dam-upload-video.md)

[Przekazanie plików innych niż obrazy i wideo](dam-upload-files.md)

[Przycinanie obrazów](dam-crop-images.md)

[Dostosowywanie punktów ogniskowych obrazu](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]