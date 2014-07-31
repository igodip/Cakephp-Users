# CakePHP Users Plugin

## Installation

Open the console and type:

    cake schema create --plugin Users

Load the plugin in the file Config/bootstrap.php

    CakePlugin::loadAll(array(
        array('routes' => true, 'bootstrap' => true, 'ignoreMissing' => true)
    ));
    
Modify the AppController.php file.

    public function beforeFilter(){
        parent::beforeFilter();
		
		if (isset($this->params['prefix']) && $this->params['prefix'] == 'admin') {
			$this->Auth->allow();
        }else{
        	$this->Auth->allow();
        }
		
	}
