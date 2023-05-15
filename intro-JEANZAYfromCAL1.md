
- - - -
# 1. JZ access:
### ssh to CAL1 from your local computer (`ssh -Y yourlogin@ige-meom-cal1.u-ga.fr`):
* Open file  `.bash_profile` or `.bashrc`in your local $home directory:

```
vi .bash_rc
```
* Edit file by adding this line:

```
alias log2CAL1=‘ssh -Y yourlogin@ige-meom-cal1.u-ga.fr’
```
* Save the file with vi: `:wq`
	

### Then ssh to JZ from CAL1 (`ssh -X yourlogin@jean-zay.idris.fr`)
* Open the file  `.bash_aliases`   in your $home on CAL1 :

```
cd $home
vi .bash_aliase
```
* And add this line in file :

```
alias log2JZ=‘ssh -X yourlogin@jean-zay.idris.fr’
```
* Save the file with vi: `:wq`
	
- - - -
# 2. Copy ssh keys
 (to avoid typing passwords)
* Full tuto here: http://www.tux-planet.fr/installer-une-cle-ssh-sur-un-serveur-distant/
* In short: 
	* On your local computer:
		*   `ssh-keygen -t rsa`
		* Then  `ssh-copy-id -I ~/.ssh/id_rsa.pub yourloginonCAL1@ige-meom-cal1.u-ga.fr`
	* On CAL1:
		*  `ssh-keygen -t rsa`
		* Then  `ssh-copy-id -I ~/.ssh/id_rsa.pub yourloginonJEANZAY@jean-zay.idris.fr`


- - - -
# 3. Jean-Zay from the terminal:
* Memo from IDRIS :  http://www.idris.fr/media/su/idrischeatsheet.pdf
* Memo from MEOM GitHub: https://github.com/meom-group/tutos/tree/master/jean-zay
* Doc IDRIS à lire: http://www.idris.fr/static/intro/doc_nouvel_utilisateur.html
	* (partie 5): accès, rappels sécurités et mot de passe.
	* **Partie 7**: **les espaces disques**

* Useful softwares and how to load them:
	* ncview
	* nco et netcdf
	* python
	* Add in your .profile (in your home): 
```
module load intel-all
module load hdf5/1.10.5-mpi
module load netcdf/4.7.2-mpi
module load netcdf-fortran/4.5.2-mpi
module load ncview
module load nco
module load climate_science/
```

* Les simulations IMHOTEP: where are the data?
https://doc-imhotep.readthedocs.io/en/latest/3-Model-outputs.html#how-to-get-access

* example 1: display the header of a netcdf files to see which variables are in it:

```
cd /gpfsstore/rech/cli/rcli002/eORCA025.L75/eORCA025.L75-IMHOTEP.GAI-S/1y/2018/
ncdump -h eORCA025.L75-IMHOTEP.GAI_y2018.1y_gridTsurf.nc
```

* example 2:  visualize several files with `ncview`:

```
cd /gpfsstore/rech/cli/rcli002/eORCA025.L75/eORCA025.L75-IMHOTEP.GAI-S/1y/
ncview  ./????/eORCA025.L75-IMHOTEP.GAI_y????.1y_gridTsurf.nc &
```

