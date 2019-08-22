---
title: Profile księgowania dostawców
description: Profile księgowania dostawców umożliwiają nadzór nad księgowaniem transakcji z dostawcami w księdze głównej.
author: abruer
manager: AnnBe
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43450c5f7ab8295b896b591880da9d0bddd955cf
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835351"
---
# <a name="vendor-posting-profiles"></a>Profile księgowania dostawców

[!include [banner](../includes/banner.md)]

Profile księgowania dostawców umożliwiają nadzór nad księgowaniem transakcji z dostawcami w księdze głównej.

<a name="vendor-posting-profiles"></a>Profile księgowania dostawców
-----------------------

Profile księgowania dostawców pozwalają na przypisywanie kont księgi głównej i ustawień dokumentów do wszystkich dostawców, grupy dostawców lub jednego dostawcy. Te ustawienia będą obowiązywać podczas tworzenia zamówień zakupu, faktur od dostawcy i płatności gotówką. W przypadku niektórych transakcji można wybrać profil księgowania, który różni się od profilów księgowania ustawionych dla transakcji na tej stronie i ma względem nich pierwszeństwo. Domyślny profil księgowania jest zdefiniowany na skróconej karcie **Księga główna i podatek** na stronie  **Parametry rozrachunków z dostawcami**. Domyślny profil księgowania jest następnie automatycznie uwzględniany w nagłówku nowych dokumentów, gdzie można go zmienić na inny profil księgowania w razie potrzeby.

Można także skojarzyć definicje księgowania transakcji z typami księgowania transakcji na stronie **Definicje księgowania transakcji** . Definicja księgowania umożliwia kontrolowanie księgowania transakcji dostawcy w księdze głównej zamiast przez profile księgowania.

## <a name="creating-a-posting-profile"></a>Tworzenie profilu księgowania
### <a name="setup"></a>**Konfiguracja**

Służy do określania kont księgowych używanych podczas księgowania transakcji z wybranym profilem księgowania. Służy do wybierania kodu konta i, jeżeli jest to możliwe, numeru konta lub grupy dla wybranego profilu księgowania. W procesie księgowania najodpowiedniejszy profil księgowania dla każdej transakcji jest wyszukiwany według najbardziej charakterystycznej kombinacji kodu konta, numeru konta lub gyupy i numeru z następującym priorytetem:

| Wartość pola **Kod konta** | Wartość pola **Numer konta/grupy**        | Priorytet wyszukiwania |
|------------------------------|---------------------------------------------|-----------------|
| **Tabela**                    | Konto określonego dostawcy                     | 1               |
| **Grupa**                    | Grupa dostawców, do której należy dostawca. | 2               |
| **Wszystkich**                      | Puste                                       | 3               |

Jeśli wszystkie transakcje dostawcy mają mieć ten sam profil księgowania, należy ustawić tylko jeden profil księgowania o wartości **Wszystko** w polu **Kod konta**. Określ następujące wartości do konfigurowania profilu księgowania.

<table>
<thead>
<tr class="header">
<th>Pole</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Profil księgowania</strong></td>
<td>Umożliwia wprowadzenie kodu profilu księgowania. Można na przykład utworzyć 2 profile księgowania, aby korzystać z jednego konta dla sald dostawcy w walucie krajowej, a z drugiego — dla sald dostawcy w walucie zagranicznej. Jedno konto można nazwać Krajowe, a drugie Zagraniczne.</td>
</tr>
<tr class="even">
<td><strong>Opis</strong></td>
<td>Umożliwia wprowadzenie opisu profilu księgowania.</td>
</tr>
<tr class="odd">
<td><strong>Kod konta</strong></td>
<td>Umożliwia określenie, czy profil księgowania dotyczy określonego dostawcy, grupy dostawców czy wszystkich dostawców:
<ul>
<li><strong>Tabela</strong> — profil księgowania dotyczy jednego dostawcy. Wybierz konto dostawcy w polu <strong>Numer konta/Numer grupy</strong>.</li>
<li><strong>Grupa</strong> — profil księgowania dotyczy grupy dostawców. Wybierz grupę dostawców w polu <strong>Numer konta/Numer grupy</strong>.</li>
<li><strong>Wszyscy</strong> — profil księgowania dotyczy wszystkich dostawców. Pole <strong>Numer konta/ Numer grupy</strong> zostaw niewypełnione.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Numer konta/grupy</strong></td>
<td>W przypadku wybrania opcji <strong>Tabela</strong> w polu <strong>Kod konta</strong> należy wybrać numer konta dostawcy skojarzony z profilem księgowania. W przypadku wybrania opcji <strong>Grupa</strong> należy wybrać grupę dostawców. W przypadku wybrania opcji <strong>Wszystko</strong> należy pozostawić to pole puste.</td>
</tr>
<tr class="odd">
<td><strong>Konto rozrachunkowe</strong></td>
<td>Umożliwia wybranie konta księgowego, które będzie używane jako konto rozrachunkowe dostawcy dla dostawców objętych tym profilem księgowania. Parametr <strong>Nie zezwalaj na ręczne wprowadzanie</strong> dla tego konta głównego zostanie oznaczony. Jeśli później usuniesz to konto z profilu księgowania, sprawdź ustawienie  opcji <strong>Nie zezwalaj na ręczne wprowadzanie wpisów </strong> na stronie <strong>Konta główne</strong>. 
<p><strong>Uwaga: </strong>Po wybraniu przełącznika <strong>Użyj definicji księgowania</strong> na stronie <strong>Parametry księgi głównej</strong> transakcja definicji księgowania dla faktur od dostawcy jest używana zamiast konta rozrachunkowego.</p>
</td>
</tr>
<tr class="even">
<td><strong>Konto rozliczeniowe</strong></td>
<td>Umożliwia wybranie konta płynności używanego przy prognozowaniu przepływów pieniężnych. To pole jest dostępne tylko po włączeniu prognozowania przepływów pieniężnych.</td>
</tr>
<tr class="odd">
<td><strong>Przedpłaty podatku</strong></td>
<td>Wybierz konto dla płatności podatków z góry.
<p><strong>Uwaga:</strong> Profil księgowania używany, gdy płatność jest oznaczona jako przedpłata jest zaznaczony w profilu <strong>Księgowanie</strong> z polem <strong>Załącznik arkusza zaliczki</strong> w obszarze <strong>Księga i podatek</strong> na stronie <strong>Parametry rozrachunków z dostawcami</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>Przyjęcie</strong></td>
<td>Wybierz konto księgowe, na którym zostały zaksięgowane informacje o niezatwierdzonych fakturach od dostawcy. Informacje są wprowadzane w arkuszu rejestru faktur. Na przykład użytkownik wprowadza najbardziej podstawowe informacje o otrzymywanych fakturach dostawców w rejestrze faktur. Podczas księgowania rejestru faktur transakcje są księgowane na koncie wprowadzonym w tym miejscu oraz w polu <strong>Konto przeciwstawne</strong>. Po zatwierdzeniu faktur zadłużenie jest przenoszone z konta przybycia na konto rozrachunkowe dostawcy.</td>
</tr>
<tr class="odd">
<td><strong>Konto przeciwstawne</strong></td>
<td>Umożliwia wybranie numeru konta przeciwstawnego używanego do księgowania niezatwierdzonych faktur dostawców, które zostały zaktualizowane przy użyciu rejestru faktur. To konto przeciwstawne działa jako konto przeciwstawne dla transakcji, które są księgowane na kontach przyjęcia. W związku z tym konto zawiera zakupy u dostawców, które nie zostały jeszcze zatwierdzone.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**Restrykcje tabeli**

Dla transakcji z tym profilem księgowania określ, czy transakcje będą rozliczane automatycznie, czy będą obliczane odsetki i czy będą wysyłane ponaglenia. Można również wybrać konto, które będzie używane podczas zamykania transakcji z wybranym profilem księgowania.

Określ następujące wartości do konfigurowania profilu księgowania.

| Pole          | Opis                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Rozliczenie** | Wybierz tę opcję, aby włączyć automatyczne rozliczanie transakcji, które mają ten profil księgowania. Jeśli ta opcja jest wyczyszczona, należy ręcznie rozliczyć transakcje na stronie **Rozliczanie otwartych transakcji**. |
| **Anuluj**     | Wybierz tę opcję, aby umożliwić anulowanie transakcji, które mają ten profil księgowania.                                                                                                               |
| **Zamknij**      | Umożliwia wybranie docelowego profilu księgowania, który ma zostać włączony po zamknięciu transakcji bieżącego profilu księgowania. Transakcja jest traktowana jako zamknięta, jeśli jest w pełni rozliczona.                                       |
