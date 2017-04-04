---
title: "Zabezpieczenia użytkowników portalu dostawców"
description: "W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców. Ta informacja ma zastosowanie tylko do lutego 2016 &amp;2016 maja wersji systemu Dynamics AX."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysUserManagement
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 3a5c6a256f8330ba238ea3c0c25f14b10a9a58e6
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-portal-user-security"></a>Zabezpieczenia użytkowników portalu dostawców

W tym artykule wyjaśniono, jak skonfigurować zabezpieczenia dla zewnętrznych dostawców używających portalu dostawców. Ta informacja ma zastosowanie tylko do lutego 2016 &amp;2016 maja wersji systemu Dynamics AX.

Funkcje portalu dostawców został zastąpiony przez dostawcę rozszerzonych funkcji współpracy w usłudze Dynamics 365 dla wersji operacji 1611. Aby uzyskać więcej informacji na temat konfigurowania zabezpieczeń dla współpracy dostawcy, zobacz [Ustawianie i obsługa współpracy dostawcy](set-up-maintain-vendor-collaboration.md). Portal dostawców pokazuje ograniczone informacje o zamówieniach zakupu zewnętrznym dostawcom. Konieczne jest prawidłowe ustawienie uprawnień użytkowników Portalu dostawców w systemie Microsoft Dynamics AX, aby dostawcy nie mieli dostępu do dodatkowych informacji w Twojej instalacji systemu Dynamics AX. **Ważne:** w przeciwieństwie do innych użytkowników dostawcy zewnętrzni nie powinni mieć przypisanej roli **SystemUser**. Rola **SystemUser** przyznaje dostęp do zestawu uprawnień, do których nie powinni mieć dostępu użytkownicy zewnętrzni.

## <a name="setting-up-a-vendor-portal-user"></a>Konfigurowanie użytkownika portalu dostawców
Przed utworzeniem konta użytkownika dla kogoś, kto będzie korzystał z Portalu dostawców, trzeba ustawić użytkownikowi możliwość współpracy na Portalu dostawców. Użyj pola **Współpraca dotycząca zamówienia zakupu** na karcie **Ogólne** na stronie **Dostawcy**. Dostawcy zewnętrzni korzystający z Portalu dostawców muszą mieć następującą konfigurację:

-   Konto użytkownika Microsoft Azure Active Directory (AAD) musi być zarejestrowane dla dostawcy na stronie **użytkowników** w systemie Dynamics AX.
-   Dostawca musi mieć rolę zabezpieczeń **Vendor (zewnętrzna)**, a nie **SystemUser **. **Uwaga:** Rola **SystemUser** jest przyznawana automatycznie podczas tworzenia nowego konta użytkownika w systemie Dynamics AX. W związku z tym należy usunąć tę rolę i potwierdzić otrzymaną wiadomość z ostrzeżeniem.
-   Użytkownik Dostawca nie powinien mieć uprawnień dodawania pól z tabel zamówienia zakupu do widoku zamówienia zakupu. Na karcie **personalizacji** na karcie **użytkowników** należy ustawić opcję **Jawne personalizacje dozwolone** jako **Nie**.
-   Konto użytkownika należy skojarzyć z zarejestrowaną osobą kontaktową. Na stronie **użytkowników** wybierz osobę kontaktową w polu **Imię i nazwisko**. Wybrana osoba powinna mieć rolę **kontakt** dla odpowiednich dostawców.

Jeśli ta sama osoba wymaga dostępu do portalu dostawców dla wielu kont dostawców (dla różnych podmiotów prawnych), każde konto użytkownika tej osoby musi być skojarzone z tą samą osobą kontaktową. Rola **dostawcy (zewnętrzna)** zawiera wszystkie podstawowe funkcje, które są niezbędne, aby korzystać z funkcji portalu dostawców. Ta konfiguracja pomaga zagwarantować, że interfejs użytkownika, który widzi użytkownik zewnętrzny, zawiera tylko odpowiednie informacje.

<a name="see-also"></a>Informacje dodatkowe
--------

[Vendor collaboration](collaborate-vendors-vendor-portal.md)


