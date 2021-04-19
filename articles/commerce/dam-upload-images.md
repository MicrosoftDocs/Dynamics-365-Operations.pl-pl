---
title: Przekazanie obrazów
description: W tym temacie opisano, jak przesyłać obrazy w kreatorze witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799236"
---
# <a name="upload-images"></a>Przekazanie obrazów

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak przesyłać obrazy w kreatorze witryny w Microsoft Dynamics 365 Commerce.

Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie obrazów, pojedynczo lub razem przy użyciu folderów. Należy zawsze przekazywać wersję obrazu z największą rozdzielczością i jakością, ponieważ element zmiany rozmiaru obrazu automatycznie zoptymalizuje obraz dla różnych wzierników i punktów przerwania.

### <a name="image-information-specified-during-upload"></a>Informacje o obrazie określone podczas przekazywania

Podczas przekazywania obrazu można określić następujące informacje.

- **Tytuł, tekst alternatywny, opis, słowa kluczowe**: metadane obrazu lub obrazów. Tytuł i tekst alternatywny są wymagane.
- **Wybierz kategorię**:
    - **Brak**: używany w przypadku obrazu lub obrazów opowieści w handlu elektronicznym.
    - **Produkt, Kategoria, odbiorca, pracownik,katalog**: używany dla obrazów lub obrazów kanału rozproszonego Dynamics 365 Commerce.
- **Publikuj zasoby po przekazaniu**: gdy to pole wyboru jest zaznaczone, obraz lub obrazy są publikowane natychmiast po przekazaniu.

> [!NOTE]
> Elementy zawartości obrazu z przypisaną kategorią są również automatycznie znakowane za pomocą słowa kluczowego, aby ułatwić wyszukiwanie składników majątku w określonej kategorii.

### <a name="naming-conventions-for-omni-channel-images"></a>Konwencje nazewnictwa dla obrazów kanału rozproszonego 

Jeśli biblioteka multimediów została skonfigurowana jako wewnętrzny obraz kanału rozproszonego, można skorzystać z kategorii obrazów w celu wskazania, do której kategorii należy przekazany obraz. Istnieje również Konwencja nazewnictwa, która powinna być stosowana w celu zapewnienia prawidłowego pobierania obrazów przez inne kanały, takie jak punkt sprzedaży (POS).

Domyślna konwencja nazewnictwa zmienia się w zależności od kategorii:
- Obrazy wykazu powinny mieć nazwę „**/katalogi/\{identyfikator_języka\}/\{nazwa_katalogu\}.jpg**”
- Obrazy kategorii powinny mieć nazwę „**/kategorie/\{nazwa_kategorii\}.png**”
- Obrazy odbiorców powinny mieć nazwę „**/odbiorcy/\{nuer_odbiorcy\}.jpg**”
- Obrazy pracowników powinny mieć nazwę „**/pracownicy/\{numer_pracownika\}.jpg**”
- Obrazy produktów powinny mieć nazwę „**/Produkty/\{numer_Produktu\}_000_001.png**”
    - 001 oznacza sekwencję obrazu i może być 001, 002, 003, 004 lub 005
- Obrazy wariantów produktów powinny mieć nazwę „**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**”
    - Na przykład: 93039 \^ \^ 2 \^ Black \^_000_001.png

## <a name="upload-an-image"></a>Przekaż obraz

Aby przekazać obraz w konstruktorze witryn, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.
1. Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.
1. W oknie Eksploratora plików przejdź do jednego lub więcej obrazów do przekazania i wybierz opcję **Otwórz**.
1. W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.
1. Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię. 
1. Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.
1. Kliknij przycisk **OK**.

## <a name="upload-a-folder-of-images"></a>Przekaż folder obrazów

Aby przekazać wiele obrazów w folderze w konstruktorze witryn, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.
1. Na pasku poleceń wybierz opcję **Przekaż \> Przekaż folder**.
1. W oknie Eksploratora plików przejdź i wybierz folder do przekazania, po czym wybierz opcję **Otwórz**.
1. W oknie dialogowym **przekazywanie elementów multimedialnych** wprowadź opcjonalne słowa kluczowe i w razie potrzeby wybierz kategorię. 
1. Jeśli chcesz opublikować obrazy w folderze po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**.
1. Kliknij przycisk **OK**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania cyfrowymi składnikami majątku](dam-overview.md)

[Przekazanie wideo](dam-upload-video.md)

[Przekaż pliki](dam-upload-files.md)

[Przycinanie obrazów](dam-crop-images.md)

[Dostosowywanie punktów ogniskowych obrazu](dam-custom-focal-point.md)

[Przekazywanie i obsługiwanie plików statycznych](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
