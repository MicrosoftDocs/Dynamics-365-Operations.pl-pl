---
title: Przekaż pliki wideo
description: W tym temacie opisano, jak przekazać pliki wideo do kreatora witryny w Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98cb4f9049509dd700cf38a5d176447f86e9c824
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097069"
---
# <a name="upload-videos"></a>Przekaż pliki wideo

[!include [banner](includes/banner.md)]

W tym temacie opisano, jak przekazać pliki wideo do kreatora witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Biblioteka mediów kreatora witryny Commerce umożliwia przekazywanie plików wideo. Należy zawsze przekazywać wersję klipu wideo z największą szybkością transmisji bitów, ponieważ film wideo zostanie automatycznie przekonwertowany na odpowiedni dla różnych wzierników i punktów przerwania.

### <a name="video-information-specified-during-upload"></a>Informacje o wideo określone podczas przekazywania

Podczas przekazywania wideo można określić następujące informacje.

- **Tytuł, opis, słowa kluczowe**: metadane klipu wideo.
- **Automatycznie Generuj podpisy kodowane**: określa, czy dla danego klipu wideo powinny być automatycznie generowane podpisy kodowane.
- **Podpis kodowany**: określa podpisy kodowane, które mają być używane.
- **Zwykły dźwięk**: określa normalną ścieżkę audio, która ma być użyta.
- **Miniatura**: określa miniaturę klipu wideo. Jeśli nie zostały określone, będą one generowane automatycznie.
- **Opisowy dźwięk**: określa opisową ścieżkę audio, która ma być użyta.

## <a name="upload-a-video"></a>Przekaż plik wideo

Aby przekazać wideo w konstruktorze witryn, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Biblioteka multimedialna**.
1. Na pasku poleceń wybierz opcję **Przekaż \> Przekaż elementy multimedialne**.
1. W oknie Eksploratora plików przejdź do jednego lub więcej plików wideo do przekazania i wybierz opcję **Otwórz**.
1. W oknie dialogowym **przekazywanie elementu multimedialnego** wprowadź wymagany tytuł i tekst alternatywny.
1. Wprowadź opcjonalny opis i słowa kluczowe, a w razie potrzeby wybierz kategorię. 
1. Jeśli chcesz opublikować obrazy po natychmiastowym przekazaniu, zaznacz pole wyboru **Publikuj elementy multimedialne po przekazaniu**
1. Kliknij przycisk **OK**.

Jeśli wiele typów zasobów jest przekazywanych jednocześnie (na przykład obrazy i pliki wideo), w oknie dialogowym **przekazywanie elementu multimedialnego** można określać tylko słowa kluczowe, niezależnie od tego, czy pliki powinny być publikowane natychmiast po przekazaniu, czy mają być automatycznie generowane podpisy kodowane dla plików wideo. Wszystkie składniki majątku mają takie same słowa kluczowe.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zarządzania cyfrowymi składnikami majątku](dam-overview.md)

[Przekaż obrazy](dam-upload-images.md)

[Przekaż pliki](dam-upload-files.md)

[Przytnij obrazy](dam-crop-images.md)

[Dostosuj punkty ogniskowe obrazu](dam-custom-focal-point.md)
