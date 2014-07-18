desc "Install dependencies"
task :init do
  exec "sudo ansible-galaxy install --role-file=ansible_galaxy_dependencies.txt"
end

desc "Upgrade to wheezy"
task :prepare do
  exec "ansible-playbook 000_prepare_wheezy.yml -l cloud"
end

desc "Install common utitilies"
task :common do
  exec "ansible-playbook 001_install_common_utilities.yml"
end

desc "Add SSH keys from GitHub"
task :github_keys do
  `ansible_playbook 002_add_ssh_keys_from_github.yml -l cloud`
end

namespace :test do

  desc "Test all"
  task :all do
    `vagrant up`
    `vagrant provision`
  end

end