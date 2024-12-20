# AI-image-project
A repository gathering models for coloring and augmenting resolution.
Ce projet a été réalisé à l'aide de peu de ressources matérielles, par des étudiants en contrat de professionnalisation sous la contrainte du temps. Il n'est malheureusement pas aussi abouti que nous l'aurions souhaité.

## Architectures proposées

| **Modèle**   | **Atout principal**                            | **Applications clés**                      |
|--------------|------------------------------------------------|--------------------------------------------|
| **ViT**      | Capture des relations globales                 | Classification, segmentation, colorisation |
| **CNN**      | Extraction efficace de caractéristiques locales| Classification, détection d'objets         |
| **U-Net**    | Récupération fine des détails spatiaux         | Segmentation, reconstruction, colorisation |
| **VGG**      | Simplicité et efficacité                      | Classification, vision par ordinateur      |
| **Pix2Pix**  | Apprentissage d'une traduction image → image   | Colorisation, super-résolution            |

## Analyse des résultats

Le CNN, sans grande surprise étant un des principes de base de la computer vision n'offre des résultats que très peu concluants. Même si l'on arrive à distinguer les tentatives et essais du modèle, voit directement que ce ne sera pas une architecture retenue.

En revanche, le modèle VGG offre des résultats extrêmement intéressants. Bien que la colorisation soit fausse, on ne peut s'empêcher de remarquer un pattern pour lequel nous n'avons trouvé aucune explication. Les images sont colorisées à l'envers ! Le bleu devient orange, le vert devient violet et le rouge devient bleu, et ce sur toutes les photos.
Quant à la résolution d'image, elle est très qualitative par rapport au peu d'entraînement et d'exemples trouvés, et surtout comparées aux autres IAs.
Cependant, il semble que cette architecture, bien que prometteuse sur un petit entraînement, ne semble pas s'améliorer fortement au fil du temps.

Le modèle ViT, basé sur un encodeur et un décodeur, déconstruit et reconstruit l'image afin de la coloriser ou de changer sa résolution. Par conséquent, les résultats se font meilleurs; mais seulement à la hauteur que permettent le dataset et le temps d'entraînement. Plus ce modèle est entraîné avec différents exemples, et plus il est performant:  et cela se reflète dans les graphique et les images affichées.
Cependant, pas soucis de manque de temps, d'exemples et de moyens, dans le cadre de notre projet cette architecture n'est pas la plus efficace.

Pix2Pix est similaire au ViT, les deux étant basés sur un système d'encodeur et de décodeur.
On peut notifier des résultats progressifs si l'on augmente le nombre d'epochs et de data, mais les résultats sur petite échelle sont peu concluants.

Le modèle U-NET est quant à lui décevant, avec un bruit uniformisé sur toutes les prédictions où l'on peut commencer à discerner les formes et couleurs, mais clairement loin derrière des modèles comme le VGG ou le ViT.


En prenant en compte tous les résultats, il devient clair que pour un besoin minime une configuration comme celle du Pix2Pix ou du CNN prend sens, mais avec une plus grande disponibilité des architectures comme celles du ViT et du VGG prendraient réellement sens et apporteraient un résultat bien plus concluant.
