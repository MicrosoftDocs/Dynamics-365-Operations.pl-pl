---
title: Szablony danych z wieloma arkuszami
description: W tym artykule opisano, jak przeprowadzić import danych przy użyciu szablonów jednostki danych programu Excel w aplikacjach finansowych i operacyjnych.
author: peakerbl
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: f0845b111afb18205677b885c91fe1585b24ab14
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108815"
---
# <a name="data-templates-with-multiple-worksheets"></a>Szablony danych z wieloma arkuszami

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Zarządzanie danymi w aplikacji obsługuje szablony Microsoft Excel dla jednostek danych. Szablony te mogą zawierać jeden lub więcej arkuszy. Szablony z wieloma arkuszami są często używane, gdy wygodne jest zarządzanie danymi w jednym pliku i importowanie go do wielu jednostek danych. Przykładem mogą być oddziały i magazyny.

## <a name="upload-a-file-once-and-map-it-to-all-entities"></a>Przekazanie pliku raz i mapowanie go do wszystkich jednostek
Przeanalizujmy przykład, w którym występuje jeden plik programu Excel z arkuszami o nazwie **Oddziały** i **Magazyny**. Aby skonfigurować projekt importu danych, należy dodać pierwszą jednostkę danych, **Oddziały**, a następnie przekazać plik. Będzie można wybrać arkusz **Oddziały** do użycia dla tej jednostki.

Jeżeli dodasz drugą jednostkę **Magazyny** bez opuszczania formularza **Dodaj plik**, wyszukiwanie arkusza umożliwi wybranie arkusza **Magazyny** bez konieczności ponownego przekazywania pliku. Jedynym powodem przekazania nowego pliku byłby fakt, że dane z arkusza **Magazyny** znajdują się w innym pliku.

![Wiele arkuszy.](./media/AddFileMultipleWorkSheets.png)

## <a name="fix-worksheet-to-entity-mapping"></a>Naprawianie mapowania arkusza w jednostce

Mapowanie arkusza w jednostce danych w zadaniu importowania można naprawić w siatce. Kolumna **Arkusz** w siatce pokazuje arkusze z pliku, który został zmapowany. Można wybrać inny arkusz z menu rozwijanego. Jeśli wybrany arkusz jest już zmapowany do jednostki w projekcie danych, system wyświetli monit o potwierdzenie zmiany. Zalecamy naprawę mapowań w siatce.

![Aktualizacja mapowania arkusza.](./media/UpdateMappings.png)

## <a name="re-map-to-a-new-file"></a>Ponowne mapowanie do nowego pliku

W przypadku gdy konieczne jest przekazanie nowej wersji tego samego pliku lub całkowicie nowego pliku dla istniejących jednostek w projekcie danych należy użyć funkcji **Dodaj plik** i dodać jednostki ponownie, tak jakby były dodawane po raz pierwszy. Przed kontynuacją system potwierdzi, że chcesz zastąpić istniejące jednostki w projekcie danych. Jednostki, które nie dodawane ponownie (ani zastępowane) będą nadal zawierać poprzednie mapowania z poprzedniego pliku.

## <a name="upload-a-file-using-run-project"></a>Przekazywanie pliku przy użyciu funkcji Uruchom projekt

Plik programu Excel można przekazać, używając opcji **Uruchom projekt** w celu wykonania projektu importu. Należy uważać, aby przekazać tylko pliki, które zawierają te same arkusze co istniejące mapowania w jednostkach danych w projekcie danych. Jeżeli w nowym przekazanym pliku arkusz nie zostanie znaleziony, system wyświetli komunikat o błędzie i zatrzyma import. Jeżeli mapowanie w arkuszu musi zostać zmienione, mapowania w projekcie danych należy najpierw zaktualizować z poziomu projektu danych przed użyciem pliku w ramach funkcji **Uruchom projekt**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

