---
title: Przekazywanie zwróconych towarów do inspekcji
description: Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bdee1ed2c7e98843e5dcfe9669e6a7c1eb11173c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810685"
---
# <a name="pass-returned-items-on-to-inspection"></a>Przekazywanie zwróconych towarów do inspekcji 

[!include [banner](../includes/banner.md)]


Rejestrując zwrócony towar, można określić, że przed zwróceniem do magazynu lub likwidacją towar powinien zostać wysłany do inspekcji.

1.  Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie pozycji**.
    
    \-lub-
    
    Wybierz kolejno opcje **Zarządzanie zapasami** \> **Arkusze** \> **Przyjęcie pozycji** \> **Przyjęcie z produkcji**.

2.  W formularzu **Arkusz lokalizacji** zarejestruj przyjęcie towaru w zwykły sposób.
    

    > [!NOTE]
    > <P>Aby uzyskać informacje o rejestrowaniu przyjęcia zwróconych towarów, zobacz <A href="register-the-receipt-of-returned-items.md">Rejestrowanie przyjęcia zwróconych towarów</A></P>



3.  Na karcie **Wartości domyślne** w obszarze **Tryb obsługi** zaznacz pole wyboru **Zarządzanie kwarantanną**.

Spowoduje to utworzenie w systemie zlecenia kwarantanny, a osoba lub dział wykonujący inspekcje odpowie na to zlecenie za pomocą formularza **Zlecenie kwarantanny**.

## <a name="see-also"></a>Informacje dodatkowe

[Poddawanie zwróconych towarów inspekcji](take-returned-items-through-inspection.md)

[Określanie sposobu likwidacji zwróconych towarów](specify-how-to-dispose-of-returned-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]