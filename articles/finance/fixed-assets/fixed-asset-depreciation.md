---
title: Amortyzacja środka trwałego
description: Ten artykuł zawiera omówienie mechanizmu amortyzacji w funkcji środków trwałych.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.form: AssetBonus, AssetBookTable
ms.openlocfilehash: 9761fc9846324d1c165274b72033e195bf4ea3e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275304"
---
# <a name="fixed-asset-depreciation"></a>Amortyzacja środka trwałego

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten artykuł zawiera omówienie mechanizmu amortyzacji w funkcji środków trwałych.

Amortyzacja jest okresową transakcją, która zwykle zmniejsza wartość środka trwałego w bilansie i jest naliczana jako wydatek na koncie wynikowym. Dlatego do uznawania okresowej amortyzacji w bilansie jest zazwyczaj używane konto główne. Konto przeciwstawne to konto w części wynikowej planu kont.

Od wersji 10.0.24 opcja konfiguracja księgi środków trwałych **Obliczanie amortyzacji dodatniej** na stronie **Księgi** umożliwia obciążenie amortyzacją środka trwałego nabytego z ujemną wartością księgową (uznanie).

## <a name="depreciation-adjustment"></a>Korekta amortyzacji
Zwykle tylko korekta do już zaksięgowanej transakcji amortyzacji jest księgowana jako korekta amortyzacji. Dlatego też zarówno konto główne, jak i konto przeciwstawne są konfigurowane w ten sam sposób, co konta amortyzacji. Korekta amortyzacji może być kwotą dodatnią lub ujemną, ale funkcjonalność konta głównego (jako konta bilansowego) oraz konta przeciwstawnego (zazwyczaj jako konta wynikowego) pozostaje taka sama.

## <a name="extraordinary-depreciation"></a>Amortyzacja dodatkowa
Amortyzacja dodatkowa działa jak amortyzacja podstawowa. W związku z tym konto główne jest używane do uznawania kwoty amortyzacji w bilansie i zmniejszania wartości środka trwałego. Konto przeciwstawne jest kontem wynikowym, na którym obliczana jest amortyzacja dla okresu obrachunkowego i jest naliczana jako wydatek. 

Amortyzacja dodatkowa działa niezależnie od amortyzacji podstawowej. Gdy amortyzacja dodatkowa jest osobnym typem transakcji, możliwe jest księgowanie i raportowanie amortyzacji dodatkowej oddzielnie od zwykłej amortyzacji.

## <a name="special-depreciation-allowance"></a>Specjalny odpis amortyzacyjny
Specjalny odpis amortyzacyjny pozwala na uzyskiwanie większych kwot amortyzacji podczas pierwszego roku użytkowania i amortyzowania składnika aktywów. Specjalne odpisy amortyzacyjne należy wykonać przed wszelkimi innymi obliczeniami amortyzacji. Specjalne odpisy amortyzacyjny są często znane dopiero na późniejszych etapach użytkowania środka trwałego, dlatego najlepiej używać tego typu amortyzacji z księgą, której zapisy nie są księgowane w księdze głównej. Można użyć funkcji okresowej Usuwanie transakcji, które nie zostały zaksięgowane w księdze głównej, aby usunąć historię transakcji dla tych ksiąg. Można wówczas usunąć historię amortyzacji dla księgi środków trwałych, zaksięgować specjalny odpis amortyzacyjny, gdy jest znany, a następnie zaksięgować pozostałe transakcje amortyzacji dla roku. 

Można utworzyć nieograniczoną liczbę rekordów specjalnego odpisu amortyzacyjnego. Po przypisaniu tych rekordów do księgi grupy środków trwałych zostaną one zastosowane do księgi środków trwałych. 

Specjalny odpis amortyzacyjny jest wprowadzany jako wartość procentowa lub jako stała kwota. Przy księgowaniu propozycji amortyzacji transakcje specjalnego odpisu amortyzacyjnego są księgowane w księdze jako transakcje oddzielne od transakcji amortyzacji.

## <a name="depreciation-calendars"></a> Kalendarze amortyzacji
Każda księga ma kalendarz, który jest używany podczas amortyzowania środków trwałych. Domyślnie jeśli nie wskażesz kalendarza w księdze, będzie ona używać kalendarza obrachunkowego księgi. Gdy profil amortyzacji skojarzony z księgą korzysta z amortyzacji w roku obrachunkowym, należy wybrać kalendarz obrachunkowy dla księgi. 

Można tworzyć udostępnione kalendarze przy użyciu strony **Kalendarze obrachunkowe** w księdze głównej.

Aby uzyskać więcej informacji, zobacz [Metody i konwencje amortyzacji](depreciation-methods-conventions.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
